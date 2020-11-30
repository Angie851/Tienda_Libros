package vista;

import javax.swing.JOptionPane;
import modelo.SqlUsuarios;
import modelo.hash;
import modelo.usuarios;

public class login extends javax.swing.JFrame {

    
    public login() {
        initComponents();
    }
    
    
    private void btnIngresarActionPerformed(java.awt.event.ActionEvent evt) {                                            
        
        SqlUsuarios modsql = new SqlUsuarios();
        usuarios mod = new usuarios();
        
        String pass = new String(txtPassword.getPassword());
        
        if(!txtUsuario.getText().equals("") && !pass.equals(""))
        {
            String nuevoPass = hash.sha1(pass);
            
            mod.setUsuario(txtUsuario.getText());
            mod.setPassword(nuevoPass);
            
            if(modsql.login(mod)){
                
                inicio.frmLog = null;
                this.dispose();
                
                Menu frmMenu = new Menu(mod);
                frmMenu.setVisible(true);
                
            }else{
                JOptionPane.showMessageDialog(null, "Datos incorectos");
            }
        }else{
            JOptionPane.showMessageDialog(null, "Debe ingesar sus datos");
        }
        
    }
    
    private void formWindowClosing(java.awt.event.WindowEvent evt) {                                   
        
        inicio.frmLog = null;
    } 
