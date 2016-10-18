# ListViewMarquee
ListView内的TextView实现动态显示跑马灯

主要是使TextView获得焦点

第一步、在item的布局文件中的TextView标签加入跑马灯的属性
            android:ellipsize="marquee"
            android:marqueeRepeatLimit="marquee_forever"
            android:focusableInTouchMode="true"
            android:focusable="true"
            
第二步、在自定义适配器adapter中加入动态显示跑马灯效果的触发事件
        我选用的是长按ItemView
        itemView.setOnLongClickListener(new View.OnLongClickListener() {
         public boolean onLongClick(View v) {
         
                    LogUtil.e("DevEditAdapter","---长按"+getAdapterPosition()+"-----");
                    
                    tvDevName.setFocusable(true);
                    
                    tvDevName.requestFocus();
                    

                    itemView.setFocusable(true);
                    
                    itemView.requestFocus();
                    

                    return true;
                    
                }
           });
