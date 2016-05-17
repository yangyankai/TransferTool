# TransferTool
Android 常用转化工具

##Android中Bitmap, Drawable, Byte,ID之间的转化 
//1.  Bitmap 转化为 byte
ByteArrayOutputStream out = new ByteArrayOutputStream();
bitmap.compress(Bitmap.CompressFormat.PNG, 100, out);
byte[] array= out.toByteArray();

//2. byte转化为bitmap
Bitmap bitmap = BitmapFactory.decodeByteArray(data, 0, data.length);

//3. bitmap转化为Drawable
Drawable drawable = new FastBitmapDrawable(bitmap);

//4. Drawable转化为bitmap
 a. BitmapDrawable, FastBitmapDrawable直接用getBitmap
 b. 其他类型的Drawable用Canvas画到一个bitmap上
      Canvas canvas = new Canvas(bitmap)
      drawable.draw(canvas)


//5.id转化graphic.drawable

   Drawable drawable = getResources().getDrawable(R.drawable.icon);


//6.id转化成Bitmap

   Bitmap bitmap = BitmapFactory. decodeResource (Resources   res, int id) 
