# Supports

## Make Supports Easy to Remove

Supports can sometimes be difficult to remove from a print. And when they are removed, they leave broken bits of plastic.

While the fancy people can use a different filament type as a support, the rest of us need another trick.


</br></br>
In the **Process** Area, go to the **Support** tab.

Apply these settings:

| Category | Setting              | Value       |
| -------- | -------------------- | ----------- |
| Support  | Enable Support       | On          |
| Support  | Type                 | Tree (auto) |
| Support  | Style                | Tree Slim   |
| Advanced | Top Z Distance       | 0.3         |
| Advanced | Top interface layers | 3           |


</br></br>
How does this work? It's mainly the two **advanced** settings.

The `top Z distance` is the size of the gap between the top of the support and the part it is supporting.

The default value for this is 0.2mm, but here it's been increased to 0.3mm. This makes the support easier to break off.


</br></br>
The top interface layers refers to how many surface layers the supports have. By default this is 2.

This has been increased to 3 to make the top of the support stronger. This means it's less likely to break up when you remove the support.



