
public class Conexion {
    private final String bd = "Libreria";
    private final String user = "root";
    private final String pass = "";
    private final String url = "jdbc:mysql://localhost:3306/"+ bd;
    private Connection con = null;
    
    public Connection getConexion()
    {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            con = (Connection) DriverManager.getConnection(url, user, pass);
           
        } catch (ClassNotFoundException ex) {
            Logger.getLogger(Conexion.class.getName()).log(Level.SEVERE, null, ex);
        } catch (SQLException ex) {
            Logger.getLogger(Conexion.class.getName()).log(Level.SEVERE, null, ex);
        }
        
        return con;
    }
    
}
