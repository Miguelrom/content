---
title: PermissionStatus
slug: Web/API/PermissionStatus
page-type: web-api-interface
browser-compat: api.PermissionStatus
---

{{APIRef("Permissions API")}}{{AvailableInWorkers}}

The **`PermissionStatus`** interface of the [Permissions API](/en-US/docs/Web/API/Permissions_API) provides the state of an object and an event handler for monitoring changes to said state.

{{InheritanceDiagram}}

## Instance properties

- {{domxref("PermissionStatus.name")}} {{ReadOnlyInline}}
  - : Returns the name of a requested permission, identical to the `name` passed to {{domxref("Permissions.query")}}.
- {{domxref("PermissionStatus.state")}} {{ReadOnlyInline}}
  - : Returns the state of a requested permission; one of `'granted'`, `'denied'`, or `'prompt'`.

### Events

- {{domxref("PermissionStatus.change_event", "change")}}
  - : Invoked upon changes to `PermissionStatus.state`.

## Example

```js
navigator.permissions
  .query({ name: "geolocation" })
  .then((permissionStatus) => {
    console.log(`geolocation permission status is ${permissionStatus.state}`);
    permissionStatus.onchange = () => {
      console.log(
        `geolocation permission status has changed to ${permissionStatus.state}`,
      );
    };
  });
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
