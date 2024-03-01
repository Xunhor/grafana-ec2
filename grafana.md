# Como Subir uma EC2 com Grafana e Monitorar a Instância com CloudWatch

Este tutorial visa fornecer um guia passo a passo sobre como provisionar uma instância EC2 na AWS e configurá-la com Grafana para monitoramento. Com Grafana, você poderá visualizar e analisar métricas importantes da sua instância EC2 em tempo real.

## Pré-requisitos

- Uma conta na AWS
- Conhecimento básico de AWS EC2
- Conhecimento básico de Grafana
- Conhecimento básico de CloudWatch

## Passos

1. **Crie uma Instância EC2 na AWS:**
   - Acesse o Console de Gerenciamento da AWS.
   - Navegue até o serviço EC2.
   - Clique em "Launch Instance" para iniciar o assistente de criação de instâncias.
   - Siga as instruções para selecionar uma AMI, configurar a instância e definir as opções de segurança.

2. **Acesse a Instância EC2 via SSH:**
   - Use seu terminal ou cliente SSH favorito para se conectar à instância EC2 usando o IP público e a chave privada associada.

3. **Instale Grafana na Instância:**
   - Atualize os pacotes do sistema: `sudo yum update`
   - Instale o Grafana: `sudo yum install -y https://dl.grafana.com/oss/release/grafana-10.3.3-1.x86_64.rpm`
   - Habilite o serviço Grafana: `sudo systemctl enable grafana-server`
   - Inicie o serviço Grafana: `sudo systemctl start grafana-server`
   - Verifique se o serviço está em execução: `sudo systemctl status grafana-server`

   - [Download oficial do Grafana](https://grafana.com/grafana/download?pg=get&plcmt=selfmanaged-box1-cta1&edition=oss)


4. **Configurar o Grafana:**
   - Acesse o Grafana no navegador usando o IP público da instância e a porta 3000 (http://[IP_DA_INSTANCIA]:3000).
   - Faça login com as credenciais padrão (usuário: admin, senha: admin).
   - Siga o assistente de configuração inicial para alterar a senha de admin.

5. **Adicione uma Fonte de Dados:**
   - No painel do Grafana, vá para "Configuration" > "Data Sources".
   - Clique em "Add data source" e selecione o tipo de fonte de dados que você deseja configurar (CloudWatch).
   - Configure os detalhes da fonte de dados conforme necessário e salve.

6. **Comece a Monitorar:**
   - Agora você está pronto para começar a monitorar sua instância EC2 com Grafana.
   - Explore os painéis pré-configurados ou crie os seus próprios para visualizar métricas importantes.

## Contribuindo

Contribuições são bem-vindas! Se você tiver sugestões de melhorias para este tutorial ou encontrar erros, sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este tutorial é distribuído sob a [Licença MIT](LICENSE).
