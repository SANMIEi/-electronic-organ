# 简易电子琴

为了玩，这么做了 快乐

## 音频：

链接：https://pan.baidu.com/s/1M4McKI34MkHib6LM0xJDOQ?pwd=kuir 
提取码：kuir

## 代码如下：

```java
package bao;

import javax.sound.sampled.*;
import javax.swing.*;
import java.applet.AudioClip;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.io.BufferedInputStream;
import java.io.IOException;
import java.io.InputStream;

public class JieMian extends JFrame {
    
    AnJian anJian = null;
    
    public static final int WIDTH = 700;
    public static final int HEIGHT = 200;
    //定义两个参数 ，分别为 宽 高
    
    public JieMian () {
        //无参构造器
        
        anJian = new AnJian();
        this.addKeyListener(anJian);
        
        this.setSize(WIDTH,HEIGHT);
        //设定窗口的宽高
        this.setVisible(true);
        //设定窗口是否可见
        this.setResizable(false);
        //设定窗口是否可以修改
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        //允许我们点×关闭进程
        this.setTitle("电子琴 按键: A1 S2 D3 F4 J5 K6 L7");
        //标题

    }
    public static void main(String[] args) {
        JieMian jieMian = new JieMian();
    }
}

class AnJian implements KeyListener {

    @Override
    public void keyTyped(KeyEvent e) {

    }

    //当我们按下按键
    @Override
    public void keyPressed(KeyEvent e) {
        System.out.println(e.getKeyCode());
        //这样我们可以知道我们按键对应的KeyCode
        //比如 A = 65
        if(e.getKeyCode() == 65) {
            try {
                Clip bgm = AudioSystem.getClip();
                String path = "/bao/music/1.wav";
                InputStream is = this.getClass().getResourceAsStream(path);
                BufferedInputStream buffer = new BufferedInputStream(is);
                AudioInputStream ais = AudioSystem.getAudioInputStream(buffer);
                bgm.open(ais);
                bgm.start();
            } catch (LineUnavailableException | UnsupportedAudioFileException | IOException ex) {
                ex.printStackTrace();
            }
        }
        //本来参考的b站另一个up的代码
        //但是我用的是java11，AudioClip没法用
        //尝试了其他的方法，但是导出jar后没法调用jar包里的wav音频文件
        //目前使用的这种方式解决了上面的问题
        //其实我自学的java还没有到这一步，不过为了玩还是这么做了
        
        //重复上面这一段
        if(e.getKeyCode() == 83) {
            try {
                Clip bgm = AudioSystem.getClip();
                String path = "/bao/music/2.wav";
                InputStream is = this.getClass().getResourceAsStream(path);
                BufferedInputStream buffer = new BufferedInputStream(is);
                AudioInputStream ais = AudioSystem.getAudioInputStream(buffer);
                bgm.open(ais);
                bgm.start();
            } catch (LineUnavailableException | UnsupportedAudioFileException | IOException ex) {
                ex.printStackTrace();
            }
        }
        if(e.getKeyCode() == 68) {
            try {
                Clip bgm = AudioSystem.getClip();
                String path = "/bao/music/3.wav";
                InputStream is = this.getClass().getResourceAsStream(path);
                BufferedInputStream buffer = new BufferedInputStream(is);
                AudioInputStream ais = AudioSystem.getAudioInputStream(buffer);
                bgm.open(ais);
                bgm.start();
            } catch (LineUnavailableException | UnsupportedAudioFileException | IOException ex) {
                ex.printStackTrace();
            }
        }
        if(e.getKeyCode() == 70) {
            try {
                Clip bgm = AudioSystem.getClip();
                String path = "/bao/music/4.wav";
                InputStream is = this.getClass().getResourceAsStream(path);
                BufferedInputStream buffer = new BufferedInputStream(is);
                AudioInputStream ais = AudioSystem.getAudioInputStream(buffer);
                bgm.open(ais);
                bgm.start();
            } catch (LineUnavailableException | UnsupportedAudioFileException | IOException ex) {
                ex.printStackTrace();
            }
        }
        if(e.getKeyCode() == 74) {
            try {
                Clip bgm = AudioSystem.getClip();
                String path = "/bao/music/5.wav";
                InputStream is = this.getClass().getResourceAsStream(path);
                BufferedInputStream buffer = new BufferedInputStream(is);
                AudioInputStream ais = AudioSystem.getAudioInputStream(buffer);
                bgm.open(ais);
                bgm.start();
            } catch (LineUnavailableException | UnsupportedAudioFileException | IOException ex) {
                ex.printStackTrace();
            }
        }
        if(e.getKeyCode() == 75) {
            try {
                Clip bgm = AudioSystem.getClip();
                String path = "/bao/music/6.wav";
                InputStream is = this.getClass().getResourceAsStream(path);
                BufferedInputStream buffer = new BufferedInputStream(is);
                AudioInputStream ais = AudioSystem.getAudioInputStream(buffer);
                bgm.open(ais);
                bgm.start();
            } catch (LineUnavailableException | UnsupportedAudioFileException | IOException ex) {
                ex.printStackTrace();
            }
        }
        if(e.getKeyCode() == 76) {
            try {
                Clip bgm = AudioSystem.getClip();
                String path = "/bao/music/7.wav";
                InputStream is = this.getClass().getResourceAsStream(path);
                BufferedInputStream buffer = new BufferedInputStream(is);
                AudioInputStream ais = AudioSystem.getAudioInputStream(buffer);
                bgm.open(ais);
                bgm.start();
            } catch (LineUnavailableException | UnsupportedAudioFileException | IOException ex) {
                ex.printStackTrace();
            }
        }
    }

    @Override
    public void keyReleased(KeyEvent e) {

    }
}
```

