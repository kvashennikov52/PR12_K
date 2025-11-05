# Квашенников Илья Сергеевич PR12
![user](https://github.com/kvashennikov52/PR12_K/blob/main/user.jpeg)
## Информация обо мне

**Учебное заведение :** Заволжский Автомоторный Техникум

**Специальность 09.02.07**

**Настроение:** *Хорошее* 😃

**Цитата:**
~~Они больше не делают баги, как Банни (Bugs Bunny).~~ -Olav Mjelde.

**github:** https://github.com/kvashennikov52

**Увлечения**
|**#**|**Название**|
|---|--------|
| 1 | Отдых | 
| 2 | Спорт |
| 3 | и тд |

### Часть моего кода

  private void btnRestore_Click(object sender, EventArgs e)
        {
            try
            {
                using (MySqlConnection con = new MySqlConnection(connStr.GetConn() + ";CharSet=utf8mb4"))
                {
                    con.Open();
                    new MySqlCommand("SET NAMES utf8mb4;", con).ExecuteNonQuery();

                    string sql = File.ReadAllText("db57_restore.sql");
                    new MySqlCommand(sql, con).ExecuteNonQuery();
                }

                MessageBox.Show("Структура БД успешно восстановлена!", "Успех", MessageBoxButtons.OK, MessageBoxIcon.Information);
                LoadTables();
            }
            catch (Exception ex)
            {
                MessageBox.Show("Ошибка при восстановлении: " + ex.Message, "Ошибка", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }
