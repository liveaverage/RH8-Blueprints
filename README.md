# RH8-Blueprints
Collection of Red Hat Enterprise Linux 8 Blueprints

# Usage

1. Pull desired blueprint: `curl <blueprint.toml> > base-rhel8.toml`
2. Push blueprint via composer: `composer-cli blueprints push base-rhel8.toml`
3. Start creation of vmdk using blueprint: `composer-cli compose start base-rhel8 vmdk`
4. Monitor composer queue: `composer-cli compose status`
5. Download the generated vmdk: `composer-cli compose image <image_UUID>`
6. Copy to desired datastore: `scp image_UUID.vmdk root@esx.host.local:/vmfs/volumes/esx1_vms_nvme1/base-rhel8.vmdk`
7. Clone vmdk to a new thin disk: `vmkfstools -i /vmfs/volumes/esx1_vms_nvme1/base-rhel8.vmdk -d thin /vmfs/volumes/esx1_vms_nvme1/rh8/rh8.vmdk`
