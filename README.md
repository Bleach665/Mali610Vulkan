# Mali610Vulkan

enable vulkan on mali610. tested on Joshua desktop image (https://github.com/Joshua-Riek/ubuntu-rockchip), Rock5c SBC

````
wget https://repo.rock-chips.com/edge/debian-release-v2.0.0/pool/main/r/rockchip-mali/rockchip-mali_1.9-12_arm64.deb

sudo dpkg -i rockchip-mali_1.9-12_arm64.deb

sudo ln -s /usr/lib/aarch64-linux-gnu/libmali-valhall-g610-g6p0-wayland-gbm-vulkan.so /usr/lib/aarch64-linux-gnu/libmali.so

sudo mkdir -p /etc/vulkan/icd.d/

echo '{
    "file_format_version": "1.0.0",
    "ICD": {
        "library_path": "/usr/lib/aarch64-linux-gnu/libmali-valhall-g610-g6p0-wayland-gbm-vulkan.so",
        "api_version": "1.0.0"
    }
}' | sudo tee /etc/vulkan/icd.d/mali.json
````
