# Quickstart for Bitasmbl project (Swift)

## 1) Install Bitasmbl-CLI package

```bash
npm i bitasmbl-cli
```

## 2) Run bitasmbl command to set up the project

```bash
bitasmbl pull --repoUrl https://github.com/he1snber8/Bitasmbl_maswift_d54_416 --appId 416 --repoId 240
```

## 3) Enter into the main directory and start coding!

```bash
cd Bitasmbl_maswift_d54_416
```

## Customize requirements in a way you like

Bitasmbl organizes development into requirements. Each requirement describes a feature or implementation goal and can define suggested file locations through a `paths` array.

The `paths` property acts as a mapping guideline, helping contributors understand where related code should live.

You can customize `paths` mappings through the `bitasmbl.json` file.

{"Requirement":"Define portfolio layout","Paths":["**/src/layouts/**","**/src/components/layout/**","**/src/pages/**","**/src/routes/**","**/app/**"]}

## Requirement Evaluation

Bitasmbl includes a requirement evaluation workflow that lets contributors select a task and submit work for validation.

Run:

```bash
bitasmbl evaluate
```

Example output:

<pre>
? Available Requirements:

❯ [<span style="color:#9333ea">1</span>] <span style="color:#9333ea"> Define portfolio layout </span>            [3]
  [2] Build showcase components            [3]
  [3] Implement navigation routing         [3]
</pre>

`[x]` on the right represents the number of submission attempts remaining for a requirement.

## Example evaluation result

```swift
/*
|--------------------------------------------------------------------------
| BITASMBL EVALUATION
|--------------------------------------------------------------------------
| REQUIREMENT:
| Implement product catalog screen
|
| SCORE: 19/100
| STATUS: FAIL ✕
|
| INSIGHT:
| The screen renders static product data and does not use a view model,
| reusable components, loading state, error handling, or async data fetching.
|--------------------------------------------------------------------------
*/

import SwiftUI

struct Product: Identifiable {
    let id: Int
    let name: String
    let price: Double
}

struct ProductCatalogView: View {
    let products = [
        Product(id: 1, name: "Keyboard", price: 89.99),
        Product(id: 2, name: "Mouse", price: 49.99)
    ]

    var body: some View {
        List(products) { product in
            HStack {
                Text(product.name)
                Spacer()
                Text("$\(product.price)")
            }
        }
        .navigationTitle("Products")
    }
}
```

## Learn More

For complete command references, workflow explanations, and additional documentation, visit:

👉 [Bitasmbl Documentation](https://bitasmbl.com/docs)
