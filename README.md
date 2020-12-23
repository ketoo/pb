1)

./vcpkg create pb https://codeload.github.com/protocolbuffers/protobuf/zip/v3.11.4 pb3.11.4.zip


2) port/pb/pb.json


vcpkg_download_distfile(ARCHIVE
    URLS "https://codeload.github.com/protocolbuffers/protobuf/zip/v3.11.4"
    FILENAME "pb3.11.4.zip"
    SHA512 17dad8a079083649572d2fab64caf9f4400c81c8814fdcf587b5560581be928b98f0f83d3240fa88c24446e6672ec7c836fb947f27c9dc6a8605631eda77b834
)

vcpkg_extract_source_archive_ex(
    OUT_SOURCE_PATH SOURCE_PATH
    ARCHIVE ${ARCHIVE}
    # (Optional) A friendly name to use instead of the filename of the archive (e.g.: a version number or tag).
    # REF 1.0.0
    # (Optional) Read the docs for how to generate patches at:
    # https://github.com/Microsoft/vcpkg/blob/master/docs/examples/patching.md
    PATCHES
        fix-static-build.patch
)