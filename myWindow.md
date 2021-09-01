package Java1Lesson8.swing.MyWindow;

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class MyWindow extends JFrame {
    private JTextField textField;
    private int randomNumber;
    public int count = 2;

    public MyWindow() {
        this.randomNumber = (int)(Math.random() * 10) + 1;
        setTitle("Let's Play - Guess the Number");
        setBounds(600, 300, 600, 200);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setResizable(false);//change of size of the window is not allowed
        textField = new JTextField();
        add(textField, BorderLayout.NORTH);
        textField.setText("Number from 1 to 10 guessed. You have 3 attempts.");
        textField.setEditable(false);
        textField.setHorizontalAlignment(SwingConstants.CENTER);

        JButton resetButton = new JButton("Start New Game!");
        add(resetButton, BorderLayout.SOUTH);
        resetButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                textField.setText("Game reset: number from 1 to 10 guessed. You have 3 attempts.");
                randomNumber = (int)(Math.random() * 10) + 1;
                count = 2;
           } });

        Font font = new Font("Arial", Font.PLAIN, 20);
        textField.setFont(font);
        JPanel buttonsPanel = new JPanel(new GridLayout(1, 10));
        add(buttonsPanel, BorderLayout.CENTER);
        for (int i=1; i <= 10; i++){
            JButton button = new JButton(String.valueOf(i));
            button.setFont(font);
            buttonsPanel.add(button);
            int buttonIndex = i;
            button.addActionListener(new ActionListener() {
                @Override
                public void actionPerformed(ActionEvent e) {
                    tryToGuess(buttonIndex);
                } });
        }
                setVisible(true);
    }
    public void tryToGuess(int number) {
        if (count > 0) {
            if (number == randomNumber) {
                textField.setText("You Won! Number is: " + randomNumber);
            } else if (number > randomNumber) {
                textField.setText("Wrong... Number is smaller than " + number + ". " + count + " attempts left.");
            } else {
                textField.setText("Wrong... Number is bigger than " + number+ ". " + count + " attempts left.");
            }
            count = count-1;
        }
        else textField.setText("Game over! Number was " + randomNumber + ".");

    }
}
