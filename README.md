# LiveMusicVis

1. Clone this repo

2. Set up Python environment. (If you have not installed Anaconda on your computer, install it via: https://www.anaconda.com/products/distribution)
```
cd livemusicvis
conda clean -a
pip cache purge
conda create -n livemusicvis python=3.9.12
conda activate livemusicvis
pip install https://github.com/ghalter/VIAN/archive/refs/heads/master.zip
pip install -r requirements.txt --no-deps
pip install jupyter
```
install essentia: (macOS using Anaconda: https://github.com/MTG/essentia/issues/777) Tensorflow module of essentia is necessary!
install librosa: ```pip install librosa```
install visual-clutter: https://github.com/kargaranamir/visual-clutter (```pip install visual-clutter --no-deps```)
force library numba to update: ```conda install -c numba numba==0.56.2```
change version of numpy for scipy: ```conda install "numpy>=1.16.5,<1.23.0"```

3. Install additional packages:
3.1 https://essentia.upf.edu/installing.html
3.1.1 for MacOS: pip install essentia

4. Set up database for backend.
4.1 Download and install Postgres: https://www.postgresql.org/download/
4.2 Download and install PgAdmin: https://www.pgadmin.org/download/
4.3 Add Database called "FilmColors_v2_Production" to your databases in PgAdmin
4.4 Add new Role "ERCAdmin": 
4.4.1 Right click on "Login/Group Roles" and then create.
4.4.2 Give all "Privileges" to this Role (see tab "Privileges")
4.5 Set new Role "ERCAdmin" as Owner for Database "FilmColors_v2_Production"
4.5.1 Right click on "FilmColors_v2_Production" database -> Properties -> set the Owner
4.6 Restore Data for "FilmColors_v2_Production" database
4.6.1 Right click on "FilmColors_v2_Production" database
4.6.2 Select "Restore"
4.6.3 In "Filename" insert the Path to the file "filmcolors_v2_production_final_state" (e.g: /Users/uensal/Documents/melike/livemusicvis/filmcolors_v2_production_final_state)
4.6.4 Click on the button "Restore"

5. Set up Frontend (Download Node.js, if you have it not already on your computer https://nodejs.org/en/download/)
```
cd livemusicvis/VIAN-Web2/frontend
npm install --all
```

6. Run script "extract features and insert into db.ipynb" in "scripts" and follow the instructions there

7. Running backend -> Run main.py from "livemusicvis/VIAN-Web2/backend/main.py" using the created Python interpreter in point 2
8. Running frontend -> execute ```npm run serve``` from the folder "livemusicvis/VIAN-Web2/frontend"

9. Log in to application:
9.1 Username: admin.admin@uzh.ch
9.2 Password: 123


