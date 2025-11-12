# rosbot3_gazebo

Este pacote reúne os artefatos de simulação do ROSbot 3 utilizados na disciplina de robótica, permitindo lançar o Gazebo com o modelo completo do robô e ferramentas auxiliares de teleoperação.

## Conteúdo
- `launch/start.launch`: script principal que inicia `gzserver`, `gzclient`, carrega o modelo via `robot_state_publisher` e adiciona o painel RQT de teleoperação.
- `urdf/rosbot3.xacro`: wrapper específico para a simulação, incluindo `rosbot3_description` e as macros de `ros_commons` (sensores, controladores e ajustes de atrito).
- `worlds/willow_garage.world`: mundo padrão usado nas aulas para experimentar navegação e sensores.

## Adições relevantes
- Integração do controlador `skid_steer_controller` com parâmetros de duas duplas de rodas e publicação de odometria.
- Ajuste opcional de atrito das rodas dianteiras via macro `remove_friction`, reduzindo travamentos durante as práticas.

## Como utilizar
1. Garanta que os pacotes `rosbot3_description` e `ros_commons` estejam construídos.
2. Inicie a simulação:
   ```bash
   ros2 launch rosbot3_gazebo start.launch
   ```
3. Use o painel RQT para enviar comandos diferenciais ou conecte o seu nó de controle aos tópicos `cmd_vel` e `/odom`.

Sinta-se à vontade para trocar o mundo padrão ou estender o launch com sensores adicionais conforme as necessidades da disciplina.