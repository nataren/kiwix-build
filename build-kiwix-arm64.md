# One time setup
```
sudo apt-get install python3-pip virtualenv

export TOP_DIR=build_dir
cd $TOP_DIR

virtualenv -p python3 ./
source bin/activate
pip3 install meson
hash -r

git clone git://github.com/ninja-build/ninja.git
cd ninja
git checkout release
./configure.py --bootstrap
mkdir ../bin
cp ninja ../bin
cd ..

git clone git@github.com:nataren/kiwix-build.git
cd kiwix-build

```

# 
```
export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimedes kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_es_medicine_novid_2017-08.zim --zim-file-size 290300506

export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimeden kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_en_medicine_novid_2017-08.zim --zim-file-size 1181464899

export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimedar kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_ar_medicine_novid_2017-08.zim  --zim-file-size 314283535

export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimedfr kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_fr_medicine_novid_2017-08.zim  --zim-file-size 292409222
```
