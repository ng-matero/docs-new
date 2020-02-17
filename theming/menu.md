# Menu Settings

The Menu service can return a Menu array, and the navigation of the application is generated dynamically based on the Menu data and associated with the route. 

The route path of each menu item is composed of the parent and child `states`. Following  is the type definition for the menu.

```ts
export interface Tag {
  color: string; // Background Color
  value: string;
}

export interface ChildrenItem {
  state: string;
  name: string;
  type: 'link' | 'sub' | 'extLink' | 'extTabLink';
  children?: ChildrenItem[];
}

export interface Menu {
  state: string;
  name: string;
  type: 'link' | 'sub' | 'extLink' | 'extTabLink';
  icon: string;
  label?: Tag;
  badge?: Tag;
  children?: ChildrenItem[];
}
```

## Route Path

Ng-Matero's menu only supports three levels, and generally, two levels are enough.

Take the two levels menu as an example: the `state` of the first-level item represents the `path` of the lazy module, and the `state` of the second-level item represents the `path` of the business component. So the final routing path of the business page is `level_1_state/level_2_state`. In a few cases, the three levels menu may be used.


Here is an example of a three levels menu. If you use the three levels menu, the `state` of the second-level item is allowed to be empty, and the final routing path is `material/autocomplete`. However, there is a problem in this case where the routing path cannot be associated with the third-level of the menu.

```json
{
  "menu": [
    {
      "state": "material",
      "name": "Material",
      "type": "sub",
      "icon": "favorite",
      "children": [
        {
          "state": "",
          "name": "Form Controls",
          "type": "sub",
          "children": [
            {
              "state": "autocomplete",
              "name": "Autocomplete",
              "type": "link"
            }
          ]
        }
      ]
    }
  ]
}
```

Regarding the three levels menu, you can take a look at the routing path of the demo example. Open the following two paths respectively to check the menu changes:

- [https://ng-matero.github.io/ng-matero/#/material/autocomplete](https://ng-matero.github.io/ng-matero/#/material/autocomplete)
- [https://ng-matero.github.io/ng-matero/#/material/data-table/paginator](https://ng-matero.github.io/ng-matero/#/material/data-table/paginator)

## Label Color

Label color needs to be filled with a legal Material color value, such as `red-500`, `blue-900`, see [colors](colors.md) for details.

## API

### MenuService

| Method          | Parameter            | Return   | Description            |
|-----------------|----------------------|----------|------------------------|
| getAll          | -                    | `Menu[]` | get menu               |
| set             | `menu: Menu[]`       | `Menu[]` | set menu               |
| add             | `menu: Menu`         | -        | add a menu item        |
| getMenuItemName | `stateArr: string[]` | `string` | get the menu item name |
| getMenuLevel    | `stateArr: string[]` | `string` | get menu levels        |