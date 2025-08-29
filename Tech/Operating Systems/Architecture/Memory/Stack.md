- A stack on the computer that stores:
    
    - The function being run
        
    - The variables
        
- Value types (static) (there are exceptions)

### ESCOPE, NOT STACK FRAME

```rust
fn main() {
    let mut x = 1;
    println!("x is: {}", x);
    {
        let x = x +1;
        println!("x is: {}", x)
    }
    x = x + 1;
    println!("x is: {}", x);

    let mut y = 1;
    println!("y is: {}", y);
    {
        y = y +1;
        println!("y is: {}", y)
    }
    y = y + 1;
    println!("y is: {}", y);
}
```

output:
x is: 1
x is: 2
x is: 2
y is: 1
y is: 2
y is: 3


why that happens, in the second x, he is defined as 2, however the third is also 2, which might look weird, why was x not considered 2 already in the thirs changing of the variable, well, that because a new x variable is being created, and that only exists in the block of function, when out of that, x is just 1 because its changes were not saved from the higher layer of the scope that changed x to be 2, in the y example, the y of the lower layer is directly changed in that block