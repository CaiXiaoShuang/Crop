## Usage
### First, declare CropImageActivity in your manifest file:
<pre><code><activity android:name="com.soundcloud.android.crop.CropImageActivity"/>
</code></pre>
## Crop
<pre><code>Crop.of(inputUri, outputUri).asSquare().start(activity)
</code></pre>
## Listen for the result of the crop (see example project if you want to do some error handling):
<pre><code>@Override
   protected void onActivityResult(int requestCode, int resultCode, Intent result) {
     if (requestCode == Crop.REQUEST_CROP && resultCode == RESULT_OK) {
          doSomethingWithCroppedImage(outputUri);
     }
   }
</code></pre>
## Some attributes are provided to customise the crop screen. See the example project theme.
## Pick
## The library provides a utility method to start an image picker:
<pre><code> Crop.pickImage(activity)
</code></pre>


