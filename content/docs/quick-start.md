+++
title = "Quick start"

date = 2020-04-06
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
weight = 40

+++
Starting from a new installation, we will configure a user who will be able to make and receive calls via a SIP trunk.

## 1. Login to the administration interface

The administation interface named `wazo-ui` is available on port `443` of your engine you can access it through an internet browser.

To log in use the user `root` and the password that you defined at the beginning of the installation.

![login](/img/quick-start/login.png)

## 2. Use tenants

### Meaning of multi-tenant
Wazo is a multi-tenant IPBX, this means that it is possible for a telephony provider to have more than one customer on the same IPBX.

A customer is compartmentalized in his environment and is not aware of users outside his company.

### Select your tenant

At the top left of the interface there is a drop-down menu, it allows you to select the tenant that you are configuring.

After installation there are two tenants on your system: 
* `master`
* `sparrow`


{{% alert warning %}}
The `master` tenant is only used by the system.
You don't have to do any configuration inside it !
{{% /alert %}}

![tenant-dorpdown](/img/quick-start/tenant-dropdown.png)

## 3. Create contexts
In the `⚙️ Advanced > 🔀 Contexts` menu we will create 3 contexts:
* `internal` context which will contain the system numbers
* `outgoing` context which will contain calls to outside
* `incall` context which will contain calls from outside

Parameter to be filled in for the internal context:
* Name: `sparrow-internal`
* Label: `sparrow-internal`
* Type: `Internal`

Parameter to be filled in for the incall context:
* Name: `sparrow-from-extern`
* Label: `sparrow-from-extern`
* Type: `Outcall`

Parameter to be filled in for the outgoing context:
* Name: `sparrow-to-extern`
* Label: `sparrow-to-extern`
* Type: `Incall`

Once the contexts are created edit the `sparrow-internal` context for:
* include the `sparrow-to-extern` context
* declare a number range for the users

![include-from-extern](/img/quick-start/include-to-extern.png)

![user-range](/img/quick-start/user-range.png)

Finally edit the `sparrow-from-extern` context to add a range for incoming calls.

![incall-range](/img/quick-start/incall-range.png)

## 4. Create a user
TODO
## 5. Create a SIP trunk
TODO
## 6. Create a incall rule
TODO
## 7. Create a outcall rule
TODO

