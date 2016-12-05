package com.example.administrator.mydemo_onepic_2.util;

import android.content.Context;
import android.database.sqlite.SQLiteDatabase;

/**
 * Created by Administrator on 2016/12/5 0005.
 * 主要对数据库操作的工具类
 */
public class DbManger {
    private static MySqliteHelper helper;
    public static MySqliteHelper getIntance(Context context){
        if (helper == null){
            helper = new MySqliteHelper(context);

        }
        return helper;
    }

    /**
     * 根据sql语句在数据库中执行语句
     * @param db    数据库对象
     * @param sql   sql语句
     */
    public static void execSQL(SQLiteDatabase db,String sql){
        if (db!=null){
            if (sql!=null && !"".equals(sql)){
                db.execSQL(sql);
            }
        }
    }
}
