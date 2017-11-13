
How to

To get a Git project into your build:

Step 1. Add the JitPack repository to your build file

    gradle
    maven
    sbt
    leiningen

Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
Copy

Step 2. Add the dependency

	dependencies {
	        compile 'com.github.CaiXiaoShuang:Crop:1.0.0'
	}

## Usage
### First, declare CropImageActivity in your manifest file:
<pre><code><activity android:name="com.soundcloud.android.crop.CropImageActivity"/>
</code></pre>
### Crop
<pre><code>Crop.of(inputUri, outputUri).asSquare().start(activity)
</code></pre>
### Listen for the result of the crop (see example project if you want to do some error handling):
<pre><code> @Override
   protected void onActivityResult(int requestCode, int resultCode, Intent result) {
     if (requestCode == Crop.REQUEST_CROP && resultCode == RESULT_OK) {
          doSomethingWithCroppedImage(outputUri);
     }
   }
</code></pre>
## Pick
### The library provides a utility method to start an image picker:
<pre><code> Crop.pickImage(activity)
</code></pre>
### How does it look?
![github](https://github.com/CaiXiaoShuang/Crop/blob/master/app/src/main/res/drawable/screenshot.png "图片")  


