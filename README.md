# Create-a-SQLite-database-connect-to-it-and-print-SQLite-version-Program
import sqlite3

try:
    sqlite_Connection = sqlite3.connect('temp.db')
    cursor = sqlite_Connection.cursor()
    print("Database created and connected to SQLite.")

    cursor.execute("select sqlite_version();")
    record = cursor.fetchall()
    print("SQLite Database Version is:", record)

except sqlite3.Error as error:
    print("Error while connecting to sqlite", error)

finally:
    if sqlite_Connection:
        sqlite_Connection.close()
        print("The SQLite connection is closed.")

Output:
Database created and connected to SQLite.
SQLite Database Version is: [('3.11.0',)]
The SQLite connection is closed.
