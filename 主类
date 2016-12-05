package com.example.administrator.mydemo_onepic_2;

import android.app.Activity;
import android.content.ContentValues;
import android.content.Context;
import android.database.sqlite.SQLiteDatabase;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

import com.example.administrator.mydemo_onepic_2.util.Constant;
import com.example.administrator.mydemo_onepic_2.util.DbManger;
import com.example.administrator.mydemo_onepic_2.util.MySqliteHelper;

/**
 * Created by Administrator on 2016/12/5 0005.
 */
public class SqliteActy extends Activity {

    Button button,button2,button3,button4,button5,button6,button7;
    MySqliteHelper helper;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_sqlite);
        helper = DbManger.getIntance(this);

        button = (Button) findViewById(R.id.button_item);
        button2 = (Button) findViewById(R.id.button_item_2);
        button3 = (Button) findViewById(R.id.button_item_3);
        button4 = (Button) findViewById(R.id.button_item_4);
        button5 = (Button) findViewById(R.id.button_item_5);
        button6 = (Button) findViewById(R.id.button_item_6);
        button7 = (Button) findViewById(R.id.button_item_7);

        button2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SQLiteDatabase db = helper.getWritableDatabase();
                String sql = "insert into "+ Constant.TABLE_NAME+" values(1,'zhangsan',20)";
                DbManger.execSQL(db,sql);
                String sql2 = "insert into "+ Constant.TABLE_NAME+" values(1,'lisi',20)";
                DbManger.execSQL(db,sql2);
                db.close();
            }
        });
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SQLiteDatabase db = helper.getWritableDatabase();

            }
        });
        button3.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SQLiteDatabase db = helper.getWritableDatabase();
                String updateSql = "update" + Constant.TABLE_NAME + "set" + Constant.NAME +
                        "='xiaoming'where" +Constant._ID + "=1";
                DbManger.execSQL(db,updateSql);
                db.close();
            }
        });
        button4.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SQLiteDatabase db = helper.getWritableDatabase();
                String delSql = "delete from" + Constant.TABLE_NAME + "where" + Constant._ID + "=2";
                DbManger.execSQL(db,delSql);
                db.close();

            }
        });
        button5.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SQLiteDatabase db = helper.getWritableDatabase();
                /**
                 * insert(String table, String nullColumnHack, ContentValues values)
                 * String table 表示插入数据表的名称
                 * ContentValues values 键为String类型hashmap集合
                 * 返回值long 表示插入数据的列数
                 */
                ContentValues values = new ContentValues();
                values.put(Constant._ID,3);
                values.put(Constant.NAME,"张三");
                values.put(Constant.AGE,30);
                long result = db.insert(Constant.TABLE_NAME,null,values);
                if (result>0){
                    Toast.makeText(SqliteActy.this,"插入数据成功！",Toast.LENGTH_SHORT).show();
                }else {
                    Toast.makeText(SqliteActy.this,"插入数据失败！",Toast.LENGTH_SHORT).show();
                }
                db.close();

            }
        });
        button6 = (Button) findViewById(R.id.button_item_6);
        button6.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SQLiteDatabase db = helper.getWritableDatabase();
                /**
                 * update(String table, ContentValues values, String whereClause, String[] whereArgs)
                 * String table表示修改数据表的名称
                 * ContentValues values 表示键为String类型的hashmap
                 * String whereClause 表示修改条件
                 * String[] whereArgs 表示修改条件的占位符
                 */
                ContentValues cv = new ContentValues();
                cv.put(Constant.NAME,"小幕"); //put(需要修改的字段名称，修改后的字段值)
                int count = db.update(Constant.TABLE_NAME,cv,Constant._ID + "=?",new String[]{"3"});
                if (count>0){
                    Toast.makeText(SqliteActy.this,"修改数据成功！",Toast.LENGTH_SHORT).show();
                }else {
                    Toast.makeText(SqliteActy.this,"修改数据失败！",Toast.LENGTH_SHORT).show();
                }
                db.close();

            }
        });
        button7.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SQLiteDatabase db = helper.getWritableDatabase();
                int count2 = db.delete(Constant.TABLE_NAME,Constant._ID+"=?",new String[]{"1"});
                if (count2>0){
                    Toast.makeText(SqliteActy.this,"删除数据成功！",Toast.LENGTH_SHORT).show();
                }else {
                    Toast.makeText(SqliteActy.this,"删除数据失败！",Toast.LENGTH_SHORT).show();
                }

            }
        });

    }
}
