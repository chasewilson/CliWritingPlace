
# Microsoft Ignite Highlights: Azure CLI

Hi everyone, as Microsoft Ignite wraps up today we’re sharing some of the latest features we released in the Azure CLI supporting
various announcements for Microsoft Ignite. We also released several important updates to Azure CLI
commands and improvements to our core platform services during the Ignite timeframe. Here are some
of the exciting announcements and updates.

(NOTE: The Azure CLI commands in the format az command --parameter that are shown below are not
intended to be run as is, they only show the key parameters that need to be used for the feature
described. Please refer to the documentation links provided to learn how to use the command with all
the required parameters.)

## Compute

**Azure VMSS flexible orchestration mode support**. With the GA release of [Azure VMSS flexible orchestration mode](https://docs.microsoft.com/azure/virtual-machines/flexible-virtual-machine-scale-sets),
Azure CLI has released several updates to support the release including updated default values for
an easier VMSS Flex creation experience and user friendly error messaging to help identify
limitations when creating scale sets with flexible orchestration.

**New `az vm/vmss --run-command` commands**. You now have more control over your [run-commands](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/run-command)
using CLI. You can `create`, `delete`, and `update` **run-commands** for a VM, place the VM into a
waiting state until a condition is met with `wait`, or get more information about your
**run-commands** using `list` and `show`! `az vm run-command create`

**Support for cross-region incremental snapshot copies.** You can now use `az snapshot --copy-start`
to create snapshots even when source and target regions are different. For example, if you need to
copy a snapshot to and edge location from your main region.

**Support for choosing Ephemeral OS disk provisioning location in CLI.** Using
`az vm/vmss create --ephemeral-os-disk`, you can choose the provisioning location with the new
`--ephemeral-os-disk-placement` preview parameter. Available options are `CacheDisk` (Cache disk) and
`ResourceDisk` (Temp disk).

**Automatic in-guest patching support for VMSS.** You can now use the new `--patch-mode` parameter
in `az vmss create` to onboard your scaled set virtual machines to [automatic in-guest patching](https://docs.microsoft.com/azure/virtual-machines/automatic-vm-guest-patching).
Multiple options or possible for Windows and Linux VMs based on your needs. For more information,
check out the [az vmss documentation](https://docs.microsoft.com/cli/azure/vmss?view=azure-cli-latest#az_vmss_create).