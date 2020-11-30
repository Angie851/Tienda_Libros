
public class inicio extends javax.swing.JFrame {

    public static login frmLog;
    public static registro frmReg;
    
    public inicio() {
        initComponents();
    }
    
    private void btnRegistrarActionPerformed(java.awt.event.ActionEvent evt) {                                             
        
        if(frmReg == null)
        {
            frmReg = new registro();
            frmReg.setVisible(true);   
        }   
    }                                            

    private void btnIniciarSesionActionPerformed(java.awt.event.ActionEvent evt) {                                                 
        
        if(frmLog == null)
        {
            frmLog = new login();
            frmLog.setVisible(true);   
        }
    }
