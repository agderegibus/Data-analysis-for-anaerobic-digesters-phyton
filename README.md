# Data-analysis-for-anaerobic-digesters-phyton
The project aims to provide a comprehensive analysis of anaerobic digesters, fostering a deeper understanding of their performance through the synthesis of diverse data sets.

import os

# Establecer el directorio de trabajo
os.chdir("/Users/valentinagirardi/Downloads/Bioinf-enero")

# Descargar Miniconda
os.system("cp Miniconda3-latest-MacOSX-x86_64.sh ~/Miniconda3-latest-MacOSX-x86_64.sh")

# Cambiar el directorio de inicio
os.chdir("~")

# Otorgar permisos de ejecución
os.system("chmod +x Miniconda3-latest-MacOSX-x86_64.sh")

# Instalación
os.system("./Miniconda3-latest-MacOSX-x86_64.sh -u -b -p $HOME/miniconda")

# Iniciar Conda
os.system("source ~/miniconda/etc/profile.d/conda.sh")

# Activar Conda
os.system("conda activate")

# Versión compatible con Conda
os.system("conda install -n base conda=4.10")
os.system("conda update -n base -c defaults conda")

# Descargar el archivo de entorno específico de QIIME 2
os.system("curl -sL \"https://data.qiime2.org/distro/core/qiime2-2020.8-py36-osx-conda.yml\" > \"qiime2.yml\"")

# Crear el entorno a partir del archivo
os.system("conda env create -n qiime2 --file qiime2.yml")

# Eliminar el archivo de configuración
os.system("rm qiime2.yml")

# Activar el nuevo entorno Conda
os.system("conda activate qiime2")

# Verificar la instalación
os.system("Qiime info")

# Configuración adicional
# Cargar canales adicionales
os.system("conda config --add channels bioconda")

# Instalar herramientas adicionales
os.system("conda install fastqc multiqc")

# Instalación de QIIME 2 Amplicon 2023
# Descargar la versión específica de QIIME 2 Amplicon
os.system("conda install wget")
os.system("wget https://data.qiime2.org/distro/amplicon/qiime2-amplicon-2023.9-py38-osx-conda.yml")

# Crear el entorno a partir del archivo
os.system("conda env create -n qiime2-amplicon-2023.9 --file qiime2-amplicon-2023.9-py38-osx-conda.yml")

# Activar el entorno QIIME 2 Amplicon
os.system("conda activate qiime2-amplicon-2023.9")
