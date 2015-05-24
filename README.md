using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Матрицы
{
    public partial class Form1 : Form
    {
        int _j2, _j1, _i1, _i2;
        public Form1()
        {

            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

      
        private void button1_Click(object sender, EventArgs e)
        {
            _i1 = Int32.Parse(textBox1.Text);
            _j1 = Int32.Parse(textBox2.Text);
            _i2 = Int32.Parse(textBox3.Text);
            _j2 = Int32.Parse(textBox4.Text);

            МатрицыЭлементы Elements = new МатрицыЭлементы(_i1, _j1, _i2, _j2, comboBox1.SelectedIndex);

            Elements.Size = new Size(100+_j1*60+_j2*60,200);

            if (comboBox1.SelectedIndex == 0 || comboBox1.SelectedIndex == 1)
            {
                if (textBox1.Text == textBox3.Text && textBox2.Text == textBox4.Text)
                { Elements.Show();}
                else { MessageBox.Show("Действие с матрицами таких размеров не возможно или есть пустые ячейки", "Ошибка", MessageBoxButtons.OK, MessageBoxIcon.Error); }
            }
            else
            {
                if ( textBox2.Text == textBox3.Text)
                { Elements.Show(); }
                else { MessageBox.Show("Действие с матрицами таких размеров не возможно или есть пустые ячейки", "Ошибка", MessageBoxButtons.OK, MessageBoxIcon.Error); }
            }
          
        }

        private void textBox1_KeyPress_1(object sender, KeyPressEventArgs e)
        {
            char ch = e.KeyChar;
            if (!Char.IsDigit(ch) && ch!=8)
            {
                e.Handled = true;
            }
        }

        private void textBox2_KeyPress(object sender, KeyPressEventArgs e)
        {
            char ch = e.KeyChar;
            if (!Char.IsDigit(ch) && ch != 8)
            {
                e.Handled = true;
            }
        }

        private void textBox3_KeyPress(object sender, KeyPressEventArgs e)
        {
            char ch = e.KeyChar;
            if (!Char.IsDigit(ch) && ch != 8)
            {
                e.Handled = true;
            }
        }

        private void textBox4_KeyPress(object sender, KeyPressEventArgs e)
        {
            char ch = e.KeyChar;
            if (!Char.IsDigit(ch) && ch != 8)
            {
                e.Handled = true;
            }
        }

        private void comboBox1_SelectedIndexChanged(object sender, EventArgs e)
        {
            
        }

   
    }
}
