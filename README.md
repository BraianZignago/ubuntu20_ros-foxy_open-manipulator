# ubuntu20_ros-foxy_open-manipulator
Repo tutorial para usar el openmanipulator


## Instalar imagen de Ubuntu

Para eso tenes que tener docker y docker-compose instalados

```bash
  sudo snap install docker
```
```bash
  sudo apt  install docker-compose
```

En la carpeta del repositorio abrimos una terminal y pegamos:
```bash
  unzip ros2-foxy.zip && cd ros2-foxy
```
Ahora es momento de montar el Docker con:
```bash
  sudo docker-compose up
```
Esperamos que se descarguen los 8GB de imagen. \
Una vez termine su instalacion podemos ingresar a ubuntu a travez del navegador por:
```bash
  http://localhost:6080 
```

## Configurar ambiente para el OPENMANIPULATOR en el navegador
Antes de nada debemos actualizar nuestro sistema:
```bash
  sudo apt update
```
```bash
  sudo apt upgrade
```
Selecionamos la distro de ros2
```bash
  source /opt/ros/foxy/setup.bash
```
Instalamos este paquete:
```bash
  sudo apt install ros-foxy-rqt* ros-foxy-joint-state-publisher

```
Creamos la workspace
```bash
  mkdir open-manipulator_ws && cd open-manipulator_ws && mkdir src && cd src
```
```bash
  git clone -b foxy-devel https://github.com/ROBOTIS-GIT/DynamixelSDK.git
```
```bash
  git clone -b ros2 https://github.com/ROBOTIS-GIT/dynamixel-workbench.git
```
```bash
  git clone -b foxy-devel https://github.com/ROBOTIS-GIT/open_manipulator.git
```
```bash
  git clone -b ros2 https://github.com/ROBOTIS-GIT/open_manipulator_msgs.git
```
```bash
  git clone -b ros2 https://github.com/ROBOTIS-GIT/open_manipulator_dependencies.git
```
```bash
  git clone -b ros2 https://github.com/ROBOTIS-GIT/robotis_manipulator.git
```
Compilamos la workspace
```bash
  cd ~/colcon_ws && colcon build --symlink-install
```
Hacemos lo siguiente:
```bash
  cd src && colcon build
```
```bash
  cd .. && colcon build
```
```bash
  source install/setup.bash
```
Ahora con eso debemos tener todo pronto para poder usar el open_manipulator. 
Para comprobar todo usamos: 
```bash
  ros2 run open_manipulator_x_controller create_udev_rules
```

Pagina oficial: https://emanual.robotis.com/docs/en/platform/openmanipulator_x/quick_start_guide/




