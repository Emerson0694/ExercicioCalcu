# ExercicioCalcu

import javax.swing.JOptionPane;

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

/**
 *
 * @author Emerson
 */
public class calculadora extends javax.swing.JInternalFrame {

    /**
     * Creates new form calculadora
     */
    private static calculadora myInstance;
    public static calculadora getInstance(){
        if (myInstance == null){
            myInstance = new calculadora();
        }
        return myInstance;
    }
    public calculadora() {
        initComponents();
    }

    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        Calculadora = new javax.swing.JPanel();
        jLabel1 = new javax.swing.JLabel();
        TxtNume1 = new javax.swing.JTextField();
        jLabel2 = new javax.swing.JLabel();
        TxtNume2 = new javax.swing.JTextField();
        jLabel3 = new javax.swing.JLabel();
        CmbOperacao = new javax.swing.JComboBox<>();
        Calcular = new javax.swing.JButton();
        lblResultado = new javax.swing.JLabel();

        setIconifiable(true);
        setMaximizable(true);
        setResizable(true);
        setTitle("Calculadora");

        Calculadora.setBorder(javax.swing.BorderFactory.createTitledBorder("Calculadora"));

        jLabel1.setText("Numero 1");

        TxtNume1.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                TxtNume1ActionPerformed(evt);
            }
        });

        jLabel2.setText("Numero2");

        jLabel3.setText("Operação");

        CmbOperacao.setModel(new javax.swing.DefaultComboBoxModel<>(new String[] { "Divisão", "Multiplicação", "Subtrair", "Soma", " " }));

        Calcular.setText("Calcular");
        Calcular.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                CalcularActionPerformed(evt);
            }
        });

        javax.swing.GroupLayout CalculadoraLayout = new javax.swing.GroupLayout(Calculadora);
        Calculadora.setLayout(CalculadoraLayout);
        CalculadoraLayout.setHorizontalGroup(
            CalculadoraLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(CalculadoraLayout.createSequentialGroup()
                .addGroup(CalculadoraLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                    .addComponent(jLabel2)
                    .addComponent(jLabel1)
                    .addComponent(jLabel3)
                    .addComponent(TxtNume1)
                    .addComponent(TxtNume2)
                    .addComponent(CmbOperacao, 0, 110, Short.MAX_VALUE)
                    .addComponent(Calcular, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                    .addComponent(lblResultado, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
                .addGap(0, 262, Short.MAX_VALUE))
        );
        CalculadoraLayout.setVerticalGroup(
            CalculadoraLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(CalculadoraLayout.createSequentialGroup()
                .addGap(12, 12, 12)
                .addComponent(jLabel1)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(TxtNume1, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(12, 12, 12)
                .addComponent(jLabel2)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(TxtNume2, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(jLabel3)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(CmbOperacao, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(18, 18, 18)
                .addComponent(Calcular)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(lblResultado, javax.swing.GroupLayout.PREFERRED_SIZE, 25, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addContainerGap(18, Short.MAX_VALUE))
        );

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(Calculadora, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                .addContainerGap())
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addComponent(Calculadora, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
        );

        pack();
    }// </editor-fold>                        

    private void TxtNume1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
    }                                        

    private void CalcularActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
        try{
        double nume1 = Double.parseDouble(TxtNume1.getText());
        double nume2 = Double.parseDouble(TxtNume2.getText());
        double Resultado = 0;
        if(CmbOperacao.getSelectedItem() == "Dividir"){
            Resultado = Operacao.dividir(nume1, nume2);
        }else if(CmbOperacao.getSelectedItem() == "Multiplicar"){
            Resultado = Operacao.multiplicar(nume1, nume2);
        }else if(CmbOperacao.getSelectedItem() == "Subtrair"){
            Resultado = Operacao.subtrair(nume1, nume2);
        }else{
            Resultado = Operacao.soma(nume1, nume2);
        }
         lblResultado.setText(""+Resultado);
    }
     catch(Exception ex){
             JOptionPane.showMessageDialog(this, "Erro ao Executar: " + ex.getMessage(), "Erro", JOptionPane.ERROR_MESSAGE);
             }
    }                                        


    // Variables declaration - do not modify                     
    private javax.swing.JPanel Calculadora;
    private javax.swing.JButton Calcular;
    private javax.swing.JComboBox<String> CmbOperacao;
    private javax.swing.JTextField TxtNume1;
    private javax.swing.JTextField TxtNume2;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JLabel jLabel2;
    private javax.swing.JLabel jLabel3;
    private javax.swing.JLabel lblResultado;
    // End of variables declaration                   
}
