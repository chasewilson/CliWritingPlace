
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
in `az vmss create` to onboard scaled set virtual machines to [automatic in-guest patching](https://docs.microsoft.com/azure/virtual-machines/automatic-vm-guest-patching).
Multiple options are possible for Windows and Linux VMs based on your needs. For more information,
check out the [az vmss documentation](https://docs.microsoft.com/cli/azure/vmss?view=azure-cli-latest#az_vmss_create).

## Storage

**Protected append support for immutable storage.** Customers can now create immutable storage
containers with the ability to append blocks to a blob. This applies to time-based retention and
legal hold policies. When creating the immutability policy for a storage container, you can use the
new `--allow-protected-append-writes` and `--allow-protected-append-writes-all` flags to enable the
ability. This doesn't enable modification of any sort to the existing content of storage containers
and can only append to the end of the container. for more information check out the [az storage container doc](https://docs.microsoft.com/cli/azure/storage/container/immutability-policy?view=azure-cli-latest#az_storage_container_immutability_policy_create).

**Update blob storage rehydration priority.** Customers can now use Azure CLI to update [archived blob storage rehydration](https://docs.microsoft.com/azure/storage/blobs/archive-rehydrate-overview)
priority with `az storage --set-tier --tier`. For more information, see the [az storage blob documentation](https://docs.microsoft.com/cli/azure/storage/blob?view=azure-cli-latest#az_storage_blob_set_tier).

**Support for no squash and all squash for NFS 3.0.**. Customers can now create or update an NFS 3.0
container to enable or disable root squash with
`az storage container-rm create/update --root-squash`. Acceptable values for `--root-squash` are
`RootSquash`, `AllSquash`, and `NoSquash`. For more information, see the [NFS protocol how-to](https://docs.microsoft.com/azure/storage/blobs/network-file-system-protocol-support-how-to)
and the [az storage container-rm](https://docs.microsoft.com/cli/azure/storage/container-rm?view)
docs.

## KeyVault

**Define policy rules under which a key can be exported.** The `--policy` parameter has been
released in public preview and customers can define policy rules using JSON or a JSON file. For more information, check out the [az keyvault create](https://docs.microsoft.com/cli/azure/keyvault/key) doc.

