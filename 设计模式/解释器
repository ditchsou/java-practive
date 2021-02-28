//练习

//请实现一个简单的解释器，它可以以SLF4J的日志格式输出字符串：

//log("[{}] start {} at {}...", LocalTime.now().withNano(0), "engine", LocalDate.now());
// [11:02:18] start engine at 2020-02-21...

//从下载练习：解释器模式练习 （推荐使用IDE练习插件快速下载）
package com.itranswarp.learnjava;

import java.time.LocalDate;
import java.time.LocalTime;

/**
 * Learn Java from https://www.liaoxuefeng.com/
 * 
 * @author liaoxuefeng
 */
public class Main {

	public static void main(String[] args) {
		log("[{}] start {} at {}...", LocalTime.now().withNano(0), "engine", LocalDate.now());
	}

	static void log(String format, Object... args) {
		int len = format.length();
		int argIndex = 0;
		StringBuilder sb = new StringBuilder(len + 20);
		char last = '\0';
		for (int i = 0; i < len; i++) {
			char ch = format.charAt(i);//复制format中的每一整个字节，保存上一位字节
			if (ch == '}') {//当字节为 } 时，删除上一位字节，插入第i参数，i自加
				if (last == '{') {
					sb.deleteCharAt(sb.length() - 1);
					sb.append(args[argIndex]);
					argIndex++;
				} else {
					sb.append(ch);
				}
			} else {
				sb.append(ch);
			}
			last = ch;
		}
		System.out.println(sb.toString());
	}
}
