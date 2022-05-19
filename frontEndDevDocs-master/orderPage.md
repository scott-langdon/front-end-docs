# Order Page Code

### Params for Shopping Carts you should look out for (will add more as i get more specifics): 

```
&clear=1
```
- Signifies that when the user adds a product, it clears out all previous product adds that the user has added previously. So in simpler terms, it just clears out the whole cart except the one the user just added

```
&bn=1
```
- When this param is NOT on the cart link, it signifies a TWO STEP checkout process. The rule of thumbs is that when you see &bn=1, we also want to use &clear=1 with it. These two params are exclusively mutual.

```
&mob=1
```
- All mobile order pages must have this parameter at the end of the cart link ( Except for wordpress pages ). It just creates a more user friendly checkout experience
