# sto
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class CheckBox_RadioButton_ComboBoxDemo extends JFrame{
    JPanel p1,p2,p3;	//面板 
    JButton b1,b2;	//普通按钮 
    JLabel lb1,lb2,lb;	//标签：lb是用于显示点击普通按钮的信息的
    JCheckBox check1,check2,check3;	//多选框 
    JRadioButton radio1,radio2;	//单选按钮 
    ButtonGroup group;	//单选按钮组
    JComboBox cb;	//组合按钮
    String name;
    String text;
    public CheckBox_RadioButton_ComboBoxDemo(){
setFont(new Font("Helvetica",Font.PLAIN, 14));
        //创建面板实例
        p1 = new JPanel();
        p2 = new JPanel();
        p3 = new JPanel();
        //创建按钮实例
        lb1 = new JLabel("特长:");
        lb2 = new JLabel("性别：");
        lb=new JLabel();
        //创建按钮实例
		b1 = new JButton("注册");
        b2 = new JButton("取消");
        check1 = new JCheckBox("音乐");
        check2 = new JCheckBox("体育");
        check3 = new JCheckBox("文艺");
        radio1 = new JRadioButton("男");
        radio2 = new JRadioButton("女");       
		setLayout(new GridLayout(5,1));	//对窗格使用网格布局
        //向界面添加面板
        add(p1);
        add(p2);
        add(p3);
        add(lb);
		group = new ButtonGroup();	//将多个单选按钮添加进组使其只能选择一个
        group.add(radio1);
        group.add(radio2);
        //向面板添加按钮
        p1.setLayout(new GridLayout(1,4));
        p1.add(lb1);
        p1.add(check1);
        p1.add(check2);
        p1.add(check3);
        p2.setLayout(new GridLayout(1,3));
        p2.add(lb2);
        p2.add(radio1);
        p2.add(radio2);
        p3.setLayout(new GridLayout(1,2));
        p3.add(b1);
        p3.add(b2); 
        this.setTitle("布局综合应用");	//设置窗口标题
        this.setSize(300,150);	//设置窗口的宽高
        this.setLocation(100,100);	//设置窗口出现对于屏幕的位置
		this.setVisible(true);	//输出窗口
//组合按钮备选项（Item）一般是放在一个字符串数组中，也可以从文件或其它Object读取。
String[] petName = {"Bird", "Cat", "Dog", "Rabbit", "Pig"};
        cb= new JComboBox(petName);
        add(cb);
		b1.addActionListener(new ActionListener(){
public void actionPerformed(ActionEvent e) {
			text="注册信息：";
if(check1.isSelected())text=text+check1.getText()+",";
if(check2.isSelected())text=text+check2.getText()+",";
if(check3.isSelected())text=text+check3.getText()+",";
if(radio1.isSelected())text=text+radio1.getText()+",";
if(radio2.isSelected())text=text+radio2.getText()+",";
text=text+cb.getSelectedItem();
			lb.setText(text);
}
});
		b2.addActionListener(new ActionListener(){
			public void actionPerformed(ActionEvent e) {
				text="";
				lb.setText(text);
			}
		});
    }
    public static void main(String[] args){
		//运行本类的构造方法
		New CheckBox_RadioButton_ComboBoxDemo();
    }  
}

