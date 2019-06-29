# Dialog
dialog 去除外边框的问题



        MyDialog myDialog=new MyDialog(MainActivity.this);
        myDialog.show();
        //需要设置属性,否则dialog的大小不起作用!必须先show再set属性
        WindowManager.LayoutParams params = myDialog.getWindow().getAttributes();
        params.width = 400;
        params.height = 300;
        View view1 = View.inflate(getApplicationContext(), R.layout.dialogview, null);
        //设置位置的属性
        Window dialogWindow = myDialog.getWindow();
        //  WindowManager.LayoutParams lp = dialogWindow.getAttributes();
        dialogWindow.setGravity(Gravity.LEFT | Gravity.TOP);

        // 必须使用这个方法,不能使用dialog.setView()的方法
        myDialog.getWindow().setContentView(R.layout.dialogview);
        dialogWindow.setAttributes(params);
