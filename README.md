# hello-world
import java.util.Date;
import javax.swing.ImageIcon;
import javax.swing.JOptionPane;
import javax.swing.UIManager;
import javax.swing.plaf.ColorUIResource;
import javax.swing.plaf.FontUIResource;
import java.awt.*;
import java.awt.Font;
import java.text.SimpleDateFormat;
import java.util.Calendar;

public class Dates extends java.applet.Applet
{
	public void init() {
		
	}
	private String x;
	public long daysBetween(Date one, Date two) {
		long difference = (one.getTime()-two.getTime())/86400000;
		return Math.abs(difference); 
	}
	public static void main(String[] args)
	{
	
	Date today = new Date();
	Calendar myNextCalendar= Calendar.getInstance();
	myNextCalendar.set(2019, 9, 11);
	
	Date nyd = myNextCalendar.getTime();
	
	Dates myObject = new Dates();
	long days = myObject.daysBetween(today,  nyd);
	
	SimpleDateFormat sdf = new SimpleDateFormat("MMMM dd, YYYY");
	String todaysDate = sdf.format(today);
	String newDay = sdf.format(nyd);
	UIManager UI=new UIManager();
	UI.put("OptionPane.background",new ColorUIResource(255,105,180));
	UI.put("Panel.background",new ColorUIResource(255,105,180));
	UI.put("OptionPane.messageForeground",new ColorUIResource(138,43,226));
	ImageIcon iconic = new ImageIcon ("ezgif-2-1bde99f5cf53.gif");
	UIManager.put("OptionPane.messageFont", new FontUIResource(new Font ("Georgia", Font.BOLD, 18)));	
	JOptionPane.showMessageDialog(null, "There are " + days + " days until Keara and Ruby are reuinted on " + newDay + "!!!","See you soon", JOptionPane.INFORMATION_MESSAGE, iconic);
	
	}
	
	
}
