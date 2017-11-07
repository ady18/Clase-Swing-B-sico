# Clase-Swing-B-sico
package graficos;
import java.awt.*;
import java.awt.Toolkit;
import javax.swing.*;

/**
 * 
 * @author Adirane
 *
 */

public class CreandoMarcoCentrado {
	
	/**Clase Toolkit:
	 * tiene dos métodos:
	 * getDefaultToolkit() y getScreenSize()
	 */

	public static void main(String[] args) {
		
		MarcoCentrado miMarco = new MarcoCentrado(); //Se instancia el objeto de la clase
		
		//Para que cuando cerremos el frame, se deje de ejecutar
		miMarco.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

		//Lo hacemos visible
		miMarco.setVisible(true);
	}

}

class MarcoCentrado extends JFrame{
	
	public MarcoCentrado(){
		
		//Para definir que se quede en el centro de la pantalla utilizamos el Toolkit
		Toolkit miPantalla = Toolkit.getDefaultToolkit();
		
		//Para proporcionar el tamaño de la ventana de acuerdo a la resolución del dispositivo
		Dimension tamanoPantalla = miPantalla.getScreenSize();
		
		//En el objeto Dimension se tiene que utilizar dos parametros enteros para width y height:
		int alturaPantalla = tamanoPantalla.height;
		int anchoPantalla = tamanoPantalla.width;
		
		//Para que el tamaño del marco esté en el medio de la pantalla la dividimos entre 2
		setSize(anchoPantalla/2,alturaPantalla/2);
		
		//Para que la localización del marco esté centralizado a la pantalla debemos definir el 1/4 
		//del tamaño de la pantalla, para eso se divide entre 4
		setLocation(anchoPantalla/4,alturaPantalla/4);
		
		setTitle("Marco Centrado");//El titulo del frame
		
		//Para cambiar el icono que aparece en el frame:
		Image miIcono = miPantalla.getImage("src/graficos/icono.png");
		//O puede ser:
		//Image miIcono = miPantalla.getImage("icono.gif");
		//Si caso esté en la carpeta del proyecto
				
		//Para establecer la imagen del icono
		setIconImage(miIcono);
	}
}
