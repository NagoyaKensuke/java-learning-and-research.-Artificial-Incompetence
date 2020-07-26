//人工無能プログラム


package com.mycompany.test;

import javax.swing.*;

import java.awt.event.*;
import java.util.regex.Pattern;

public class TEST {

    /**
     *
     * @param args the command line arguments
     *
     */
    static JFrame myframe = new JFrame("Eliza");

    static JTextField mytextfield = new JTextField();

    static JButton mybutton = new JButton("OK");

    static JTextArea mytextarea = new JTextArea();

    static Eliza myEliza = new Eliza();

    public static void main(String[] args) {

// TODO code application logic here
        myframe.setBounds(100, 100, 640, 480);

        myframe.setVisible(true);

        myframe.setLayout(null);

        myframe.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        myframe.add(mytextfield);

        mytextfield.setBounds(10, 10, 500, 50);

        myframe.add(mytextarea);

        mytextarea.setBounds(10, 70, 600, 360);

        myframe.add(mybutton);

        mybutton.setBounds(520, 10, 100, 50);

        mybutton.addActionListener(
                new ActionListener() {

            public void actionPerformed(ActionEvent e) {

//ボタンをクリックした場合の処理
                mytextarea.setText(mytextarea.getText() + "\n"
                        + mytextfield.getText() + "\n"
                        + "Eliza:「"
                        + myEliza.talk(mytextfield.getText()) + "」");

            }

        }
        );

    }

}

//Elizaクラス
class Eliza {

    public String talk(String str1) {

        int k1 = 0, k2 = 0, k3 = 0, k4 = 0;

        //「こんにちは」が含まれるか判断
        k1 = str1.indexOf("こんにちは");

        if (k1 >= 0) {
            return ("ちわ！");
        }

        //私は○○が嫌いに対応
        k3 = str1.indexOf("私は");

        k4 = str1.indexOf("が嫌い");

        if (k3 >= 0 && k4 >= 0) {

            String str3 = str1.substring(k3 + 2, k4);

            return ("あなたが嫌いなのは「" + str3 + "」ですね？");

        }

        //私は○○が好きに対応
        k1 = str1.indexOf("私は");

        k2 = str1.indexOf("が好き");

        if (k1 >= 0 && k2 >= 0) {

            String str2 = str1.substring(k1 + 2, k2);

            return ("あなたが好きなのは「" + str2 + "」ですね？");

        }

        //どんな食べ物が好き？
        k1 = str1.indexOf("食べ物");

        k2 = str1.indexOf("好き");

        if (k1 >= 0 && k2 >= 0) {

            java.util.Date d = new java.util.Date();

            long t = d.getTime();

            if (t % 3 == 0) {
                return ("Elizaは夏みかんが好き．");
            } else if (t % 3 == 1) {
                return ("あなたは，何が好きなの？");
            } else {
                return ("今，おなかいっぱい．");
            }

        }
        //英語語彙
        if (Pattern.matches("^[A-Za-z0-9]+$", str1)) {

            String[][] eng = {{"OMG", "Oh my god"}, {"Are you", "I am AI"}, {"hallo", "hallo"}, {"yeah", "yeah"}};

            for (String[] eng2 : eng) {
                if (str1.contains(eng2[0])) {
                    return eng2[1];
                }

            }
        }
        //日本語語彙
        String[][] jpn = {{"OMG", "Oh my god"}, {"どうも", "どうも"}, {"あなたは", "私はAI"}, {"私は", "そーなのかー"}, {"君は", "私はAI"}};

        for (String[] jpn2 : jpn) {
            if (str1.contains(jpn2[0])) {
                return jpn2[1];
            }
        }

        return "え，何？";

    }
}
