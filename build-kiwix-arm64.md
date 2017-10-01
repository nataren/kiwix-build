# One time setup
```
sudo apt-get install python3-pip virtualenv default-jdk-headless default-jre-headless

export TOP_DIR=build_dir
mkdir -p $TOP_DIR
cd $TOP_DIR

virtualenv -p python3 ./
source bin/activate
pip3 install meson pillow
hash -r

git clone git://github.com/ninja-build/ninja.git
cd ninja
git checkout release
./configure.py --bootstrap
mkdir ../bin
cp ninja ../bin
cd ..

git clone https://github.com/nataren/kiwix-build.git
mkdir -p ~/.gradle/
echo "org.gradle.jvmargs=-XX\:MaxHeapSize\=10g -Xmx10g" >> ~/.gradle/gradle.properties
cd kiwix-build

```

# You can run these commands as many times as you want.

Make sure to update the `VERSION_CODE`, `CONTENT_VERSION_CODE`, and `VERSION_NAME` when you are using a newer ZIM file, or when the date of the build has changed. You can find out how to build those values in the [documentation](https://github.com/kiwix/kiwix-build/wiki/Build-and-publish-a-custom-app-locally-(without-travis)#build-custom-app-apk)

```
export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimedes kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_es_medicine_novid_2017-08.zim --zim-file-size 290300506

export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimeden kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_en_medicine_novid_2017-08.zim --zim-file-size 1181464899

export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimedar kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_ar_medicine_novid_2017-08.zim  --zim-file-size 314283535

export VERSION_CODE=1172710; export CONTENT_VERSION_CODE=117271; export VERSION_NAME=2017-08; python ./kiwix-build.py --target-platform android_arm --android-custom-app wikimedfr kiwix-android-custom --zim-file-url https://download.kiwix.org/zim/wikipedia/wikipedia_fr_medicine_novid_2017-08.zim  --zim-file-size 292409222
```
