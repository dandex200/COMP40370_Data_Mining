sudo systemctl start postgresql
sudo systemctl enable postgresql

First Attempt: 
    sudo -u postgres createuser dandex
    sudo -u postgres createdb dandex_db
    sudo -u postgres psql
    ALTER USER dandex WITH PASSWORD 'ucdschool';
    GRANT ALL PRIVILEGES ON DATABASE dandex_db TO dandex;
    GRANT CREATE ON SCHEMA public TO dandex;
    \q
    
    
# View databases created
    sudo -u postgres psql -c "\l"
    
# View Users created
    sudo -u postgres psql -c "\du"

# Fix ident error postgresql
    sudo -i #To get to root
    cd /var/lib/pgsql/data
    gnome-text-editor pg_hba.conf
    CHANGE ALL ident to md5
    sudo service postgresql restart 
    This link and CGPT combined helped me: https://tecadmin.net/fatal-ident-authentication-failed-for-user-postgres/ 
    
