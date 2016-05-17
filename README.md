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
   
   
#单位转化
  public class DisplayUtil {  
        /** 
         * 将px值转换为dip或dp值，保证尺寸大小不变 
         *  
         * @param pxValue 
         * @param scale 
         *            （DisplayMetrics类中属性density） 
         * @return 
         */  
        public static int px2dip(Context context, float pxValue) {  
            final float scale = context.getResources().getDisplayMetrics().density;  
            return (int) (pxValue / scale + 0.5f);  
        }  
      
        /** 
         * 将dip或dp值转换为px值，保证尺寸大小不变 
         *  
         * @param dipValue 
         * @param scale 
         *            （DisplayMetrics类中属性density） 
         * @return 
         */  
        public static int dip2px(Context context, float dipValue) {  
            final float scale = context.getResources().getDisplayMetrics().density;  
            return (int) (dipValue * scale + 0.5f);  
        }  
      
        /** 
         * 将px值转换为sp值，保证文字大小不变 
         *  
         * @param pxValue 
         * @param fontScale 
         *            （DisplayMetrics类中属性scaledDensity） 
         * @return 
         */  
        public static int px2sp(Context context, float pxValue) {  
            final float fontScale = context.getResources().getDisplayMetrics().scaledDensity;  
            return (int) (pxValue / fontScale + 0.5f);  
        }  
      
        /** 
         * 将sp值转换为px值，保证文字大小不变 
         *  
         * @param spValue 
         * @param fontScale 
         *            （DisplayMetrics类中属性scaledDensity） 
         * @return 
         */  
        public static int sp2px(Context context, float spValue) {  
            final float fontScale = context.getResources().getDisplayMetrics().scaledDensity;  
            return (int) (spValue * fontScale + 0.5f);  
        }  
    }  
