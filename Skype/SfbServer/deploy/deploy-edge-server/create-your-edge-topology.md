---
title: Criar a topologia de borda para Skype for Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumo: Saiba como criar, publicar e exportar a topologia de servidor de borda no Skype para Business Server.'
ms.openlocfilehash: 32273f7e0cf14b4ed5be3956eb69ef66a3b06fee
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223814"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Criar a topologia de borda para Skype for Business Server
 
**Resumo:** Saiba como criar, publicar e exportar a topologia de servidor de borda no Skype para Business Server.
  
Construtor de topologia é a ferramenta que você precisa usar para construir sua topologia de servidor de borda, assim como ele é usado para qualquer componente de topologia para Skype para servidor de negócios. Antes de seguir as etapas abaixo, você precisará tenha configurado pelo menos um pool de Front-End ou um servidor Standard Edition.
  
Neste artigo, abordamos os seguintes tópicos:
  
- Criar sua topologia de servidor de borda
    
- Publicar sua topologia do Servidor de Borda
    
- Exportar sua topologia do Servidor de Borda
    
  > [!NOTE]
  > Para seguir as etapas abaixo, você precisará se registrar nos servidores de domínio mencionados abaixo como um usuário que é membro dos seguintes grupos de domínio: 
  
- RTCUniversalServerAdmins
    
- Admins. do Domínio
    
## <a name="build-your-edge-server-topology"></a>Criar sua topologia de servidor de borda

A primeira etapa na implantação está criando seu Skype para topologia de servidor de borda do Business Server, que consiste em uma das três opções:
  
- Um único servidor de borda
    
- Um pool de borda com balanceamento de carga do DNS (um ou mais servidores)
    
- Uma carga de hardware balanceada pool de borda (um ou mais servidores)
    
Se você não souber com certeza do que precisa, é uma boa hora para consultar a documentação de Planejamento antes de começar a seguir estas etapas. Caso contrário, vamos começar.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definindo a topologia para um único servidor de borda

1. Faça logon em seu Skype para Business Server Standard Edition ou um Skype para pool de Front End do servidor de negócios.
    
2. Uma vez lá, abra **Skype para o construtor de topologia de servidor de negócios**.
    
3. Na árvore de console, expanda o site que você pretende implantar o servidor de borda para.
    
4. Clique com o botão **pools de borda**e clique em **novo pool de borda**.
    
5. Você vai clicar em **Avançar** na tela **Definir novo pool de borda** .
    
6. Na tela **definir o FQDN do pool de borda** , digite o nome de domínio totalmente qualificado (FQDN) interno que o servidor de borda irá usar e selecione **pool de computador único**, clicando em **próximo** ao terminar.
    
7. Na tela **Selecionar recursos**, você tem uma escolha:
    
   - Talvez você pretende usar o mesmo endereço IP e FQDN para seu serviço de acesso SIP, sua Skype para serviço de Webconferência de servidor de negócios e seu uma / serviço de borda V. Se esse for o caso, você deve marcar a caixa de seleção **Use um único FQDN e endereço IP** (e lembre-se disso na Etapa 9 abaixo)
    
   - Se você planejar habilitar a federação, marque a caixa de seleção **Habilitar federação para este servidor de Borda (porta 5061)**.
    
8. Depois de clicar em **Próximo**, você chegará na tela **Opções de IP**. Suas opções são:
    
   - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
   Eles são bastante auto-explicativos, se você estiver usando endereços IPv4 ou IPv6, e você estiver aplicando esses endereços em seu servidor de borda interna ou externamente (você precisará ter isto em mente para a etapa 10). Você também tem a opção de configurar seu servidor de borda ou pool de borda para usar um endereço NAT (conversão) de endereço de rede para o endereço IP externo. Você pode fazer isso marcando a caixa de seleção **O endereço IP externo deste pool de Borda é convertido pelo NAT**. Clique em **Avançar** quando estiver pronto.
    
9. Na tela de FQDNs Externos, suas opções dependem da seleção feita na Etapa 7 acima.
    
   - Se você marcou a caixa de seleção **usar um único FQDN e o endereço IP** , você precisa inserir seu FQDN externo único na caixa **Acesso SIP** . Em seguida, você precisará digitar números de porta diferente para cada serviço de borda para permitir que todos eles conectem independentemente. Recomendamos 5061 para o serviço de Borda de **Acesso SIP**, 444 para o serviço de Borda de **Webconferência** e 443 para o serviço de Borda **A/V**. Clique em **Avançar** quando terminar.
    
   - Se você não marcar a caixa de seleção **usar um único FQDN e endereço IP** , você precisará inserir os FQDNs externos três para o serviço de borda de **Acesso SIP** , o serviço de borda de **Webconferência** , agora e a **A / V** serviço de borda. Clique em **Avançar** quando terminar.
    
10. Agora você está na tela **definir o endereço IP interno** . Aqui você vai digitar o endereço IP do seu servidor de borda nas caixas de texto **endereço IPv4 interno** e um **endereço IPv6 interna** , conforme as escolhas feitas novamente na etapa 8. Clique em **Avançar** quando terminar.
    
11. Na tela **Definir o endereço IP externo**, você tem algumas opções dependendo de suas escolhas anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmativo, digite seu endereço IPv4 ou IPv6 externo (aquele que estiver usando) na caixa de texto de **Acesso SIP** e, em seguida, clique em **Avançar**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se for esse o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de borda de **Acesso SIP** , o serviço de borda de **Webconferência** e o **A / V** serviço de borda e clique em **Avançar**.
    
    > [!NOTE]
    > Se você não escolheu habilitar e atribuir endereços IPv6 anteriormente, você não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
12. Se você optar por usar NAT novamente na etapa 8, agora você obterá uma tela com uma caixa de texto **endereço IP público** . Você precisará inserir o endereço IPv4 e/ou IPv6 público você configurou para A / serviço de borda de V, a serem convertidos pelo NAT. Clique em **Avançar**.
    
13. A próxima tela é **Definir o próximo salto**. Na caixa **pool de próximo salto** , selecione o nome do seu pool interno, que pode ser um pool de Front-End ou um pool autônomo. Se você tiver um diretor em seu ambiente, você deve escolher o diretor. Then click **Next**.
    
14. Na tela **associar Front End pools** , você precisará especificar um ou mais pools internos, incluindo os pools de Front-End e servidores Standard Edition, para associar a esse servidor de borda. Escolha os nomes dos pools internos desejado usando esse servidor de borda para se comunicar com usuários externos com suporte. Click **Next**.
    
    > [!NOTE]
    > Algo que deve ter em mente aqui é, se os seus pools internos ou servidores autônomos já estiver usando um Skype diferente para o servidor de borda do servidor de negócios, eles não podem ter várias associações. Se você escolher um pool interno ou um servidor autônomo que é nessa situação, você verá a aparecer um aviso informando sobre o servidor de borda, e você pode decidir se deseja continuar ou não. Se você prosseguir com essa nova associação, a conexão com o outro Servidor de Borda será interrompida. 
  
15. Clique em **Concluir** na próxima tela.
    
16. Agora você vai ser capaz de publicar essa tecnologia atualizada e siga as instruções em [Implantar servidores de borda no Skype para Business Server](deploy-edge-servers.md) para implantar no servidor de borda a partir daqui.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definindo a topologia para um DNS com balanceamento de carga pool do servidor de borda

1. Faça logon em seu Skype para Business Server Standard Edition ou um Skype para Business Server servidor Front-End.
    
2. Uma vez lá, abra **Skype para o construtor de topologia de servidor de negócios**.
    
3. Na árvore de console, expanda o site que você pretende implantar o servidor de borda para.
    
4. Clique com o botão **pools de borda**e clique em **novo pool de borda**.
    
5. Você vai clicar em **Avançar** na tela **Definir novo pool de borda** .
    
6. Na tela **definir o FQDN do pool de borda** , digite o nome de domínio totalmente qualificado (FQDN) interno que o pool de borda irá usar e selecione **pool de vários computadores**, clicando em **próximo** ao terminar.
    
7. Na tela **Selecionar recursos**, você tem uma escolha:
    
    - Talvez você pretende usar o mesmo endereço IP e FQDN para seu serviço de acesso SIP, sua Skype para serviço de webconferência Business Server e seu uma / serviço de borda V. Se esse for o caso, você deve marcar a caixa de seleção **Use um único FQDN e endereço IP** (e lembre-se disso na Etapa 9 abaixo)
    
    - Se você planejar habilitar a federação, marque a caixa de seleção **Habilitar federação para este servidor de Borda (porta 5061)**.
    
8. Depois de clicar em **Próximo**, você chegará na tela **Opções de IP**. Suas opções são:
    
    - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
     Eles são bastante auto-explicativos, se você estiver usando endereços IPv4 ou IPv6, e você estiver aplicando esses endereços em seu servidor de borda interna ou externamente (você precisará ter isto em mente para a etapa 11). Você também tem a opção de configurar seu servidor de borda ou pool de borda para usar um endereço NAT (conversão) de endereço de rede para o endereço IP externo. Você pode fazer isso marcando a caixa de seleção **O endereço IP externo deste pool de Borda é convertido pelo NAT**. Clique em **Avançar** quando estiver pronto.
    
9. Na tela de FQDNs Externos, suas opções dependem da seleção feita na Etapa 7 acima.
    
   - Se você marcou a caixa de seleção **usar um único FQDN e o endereço IP** , você precisa inserir seu FQDN externo único na caixa **Acesso SIP** . Em seguida, você precisará digitar números de porta diferente para cada serviço de borda para permitir que todos eles conectem independentemente. Recomendamos 5061 para o serviço de Borda de **Acesso SIP**, 444 para o serviço de Borda de **Webconferência** e 443 para o serviço de Borda **A/V**. Clique em **Avançar** quando terminar.
    
   - Se você não marcar a caixa de seleção **usar um único FQDN e endereço IP** , você precisará inserir os FQDNs externos três para o serviço de borda de **Acesso SIP** , o serviço de borda de **Webconferência** , agora e a **A / V** serviço de borda. Clique em **Avançar** quando terminar.
    
10. Agora você chegou a tela de **definir os computadores neste pool** . Clique no botão **Adicionar**.
    
11. Agora você está na tela **definir o endereço IP interno** . Aqui você vai digitar o endereço IP do seu servidor de borda nas caixas de texto **endereço IPv4 interno** e um **endereço IPv6 interna** , conforme as escolhas feitas novamente na etapa 8. Clique em **Avançar** quando terminar.
    
12. Na tela **Definir o endereço IP externo**, você tem algumas opções dependendo de suas escolhas anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmativo, digite seu endereço IPv4 ou IPv6 externo (aquele que estiver usando) na caixa de texto de **Acesso SIP** e, em seguida, clique em **Avançar**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se for esse o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de borda de **Acesso SIP** , o serviço de borda de **Webconferência** e o **A / V** serviço de borda e clique em **Avançar**.
    
    > [!NOTE]
    > Se você não escolheu habilitar e atribuir endereços IPv6 anteriormente, você não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
13. Clique em **Concluir**. O servidor de borda que você acabou de criar agora deve estar listado na caixa de diálogo **definir os computadores neste pool** .
    
14. Enquanto ainda estiver na tela **definir os computadores neste pool** , clique no botão **Adicionar** novamente e repita as etapas 11 a 13 até que você tenha adicionado todos os servidores de borda que pretende ter neste pool. Quando terminar, clique em **Avançar**.
    
15. Se você optar por usar NAT novamente na etapa 8, agora você obterá uma tela com uma caixa de texto **endereço IP público** . Você precisará inserir o endereço IPv4 e/ou IPv6 público você configurou para A / serviço de borda de V, a serem convertidos pelo NAT. Clique em **Avançar**.
    
16. A próxima tela é **Definir o próximo salto**. Na caixa **pool de próximo salto** , selecione o nome do seu pool interno, que pode ser um pool de Front-End ou um pool autônomo. Se você tiver um diretor em seu ambiente, você deve escolher o diretor. Then click **Next**.
    
17. Na tela **associar Front End pools** , você precisará especificar um ou mais pools internos, incluindo os pools de Front-End e pools Standard Edition, para associar a esse servidor de borda. Escolha os nomes dos pools internos desejado usando esse servidor de borda para se comunicar com usuários externos com suporte. Click **Next**.
    
    > [!NOTE]
    > Algo que deve ter em mente aqui é, se os seus pools internos ou servidores autônomos já estiver usando um Skype diferente para o servidor de borda do servidor de negócios, eles não podem ter várias associações. Se você escolher um pool interno ou um servidor autônomo que é nessa situação, você verá a aparecer um aviso informando sobre o servidor de borda, e você pode decidir se deseja continuar ou não. Se você prosseguir com essa nova associação, a conexão com o outro Servidor de Borda será interrompida. 
  
18. Clique em **Concluir** na próxima tela.
    
19. Agora você vai ser capaz de publicar essa tecnologia atualizada e siga as instruções em [Implantar servidores de borda no Skype para Business Server](deploy-edge-servers.md) para implantar no servidor de borda a partir daqui.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definindo a topologia para uma carga de hardware balanceada pool do servidor de borda

1. Faça logon em seu Skype para Business Server Standard Edition ou um Skype para Business Server servidor Front-End.
    
2. Uma vez lá, abra **Skype para o construtor de topologia de servidor de negócios**.
    
3. Na árvore de console, expanda o site que você pretende implantar o servidor de borda para.
    
4. Clique com o botão **pools de borda**e clique em **novo pool de borda**.
    
5. Você vai clicar em **Avançar** na tela **Definir novo pool de borda** .
    
6. Na tela **definir o FQDN do pool de borda** , digite o nome de domínio totalmente qualificado (FQDN) interno que o pool de borda irá usar e selecione **pool de vários computadores**, clicando em **próximo** ao terminar.
    
7. Na tela **Selecionar recursos**, você tem uma escolha:
    
   - Talvez você pretende usar o mesmo endereço IP e FQDN para seu serviço de acesso SIP, sua Skype para serviço de webconferência Business Server e seu uma / serviço de borda V. Se esse for o caso, você deve marcar a caixa de seleção **Use um único FQDN e endereço IP** (e lembre-se disso na Etapa 9 abaixo)
    
   - Se você planejar habilitar a federação, marque a caixa de seleção **Habilitar federação para este servidor de Borda (porta 5061)**.
    
8. Depois de clicar em **Próximo**, você chegará na tela **Opções de IP**. Suas opções são:
    
   - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
     Eles são bastante auto-explicativos, se você estiver usando endereços IPv4 ou IPv6, e você estiver aplicando esses endereços em seu servidor de borda interna ou externamente (você precisará ter isto em mente para a etapa 11).
    
     > [!NOTE]
     > Diferentemente de outras duas opções de topologia, ao usar um balanceador de carga de hardware, você **Não deve** selecionar a opção **o endereço IP externo do Pool de borda é convertido por NAT**. Essa opção **não é suportada**.
  
9. Na tela de FQDNs Externos, suas opções dependem da seleção feita na Etapa 7 acima.
    
   - Se você marcou a caixa de seleção **usar um único FQDN e o endereço IP** , você precisa inserir seu FQDN externo único na caixa **Acesso SIP** . Em seguida, você precisará digitar números de porta diferente para cada serviço de borda para permitir que todos eles conectem independentemente. Recomendamos 5061 para o serviço de Borda de **Acesso SIP**, 444 para o serviço de Borda de **Webconferência** e 443 para o serviço de Borda **A/V**. Clique em **Avançar** quando terminar.
    
   - Se você não marcar a caixa de seleção **usar um único FQDN e endereço IP** , você precisará inserir os FQDNs externos três para o serviço de borda de **Acesso SIP** , o serviço de borda de **Webconferência** , agora e a **A / V** serviço de borda. Clique em **Avançar** quando terminar.
    
10. Agora você chegou a tela de **definir os computadores neste pool** . Clique no botão **Adicionar**.
    
11. Agora você está na tela **definir o endereço IP interno** . Aqui você vai digitar o endereço IP do seu servidor de borda nas caixas de texto **endereço IPv4 interno** e um **endereço IPv6 interna** , conforme as escolhas feitas novamente na etapa 8. Clique em **Avançar** quando terminar.
    
12. Na tela **Definir o endereço IP externo**, você tem algumas opções dependendo de suas escolhas anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmativo, digite seu endereço IPv4 ou IPv6 externo (aquele que estiver usando) na caixa de texto de **Acesso SIP** e, em seguida, clique em **Avançar**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se for esse o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de borda de **Acesso SIP** , o serviço de borda de **Webconferência** e o **A / V** serviço de borda e clique em **Avançar**.
    
    > [!NOTE]
    > Se você não escolheu habilitar e atribuir endereços IPv6 anteriormente, você não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
13. Clique em **Concluir**. O servidor de borda que você acabou de criar agora deve estar listado na caixa de diálogo **definir os computadores neste pool** .
    
14. Enquanto ainda estiver na tela **definir os computadores neste pool** , clique no botão **Adicionar** novamente e repita as etapas 11 a 13 até que você tenha adicionado todos os servidores de borda que pretende ter neste pool. Quando terminar, clique em **Avançar**.
    
15. A próxima tela é **Definir o próximo salto**. Na caixa **pool de próximo salto** , selecione o nome do seu pool interno, que pode ser um pool de Front-End ou um pool autônomo. Se você tiver um diretor em seu ambiente, você deve escolher o diretor. Then click **Next**.
    
16. Na tela **associar Front End pools** , você precisará especificar um ou mais pools internos, incluindo os pools de Front-End e pools Standard Edition, para associar a esse servidor de borda. Escolha os nomes dos pools internos desejado usando esse servidor de borda para se comunicar com usuários externos com suporte. Click **Next**.
    
    > [!NOTE]
    > Algo que deve ter em mente aqui é, se os seus pools internos ou servidores autônomos já estiver usando um Skype diferente para o servidor de borda do servidor de negócios, eles não podem ter várias associações. Se você escolher um pool interno ou um servidor autônomo que é nessa situação, você verá a aparecer um aviso informando sobre o servidor de borda, e você pode decidir se deseja continuar ou não. Se você prosseguir com essa nova associação, a conexão com o outro Servidor de Borda será interrompida. 
  
17. Clique em **Concluir** na próxima tela.
    
18. Agora você vai ser capaz de publicar essa tecnologia atualizada e siga as instruções em [Implantar servidores de borda no Skype para Business Server](deploy-edge-servers.md) para implantar no servidor de borda a partir daqui.
    
## <a name="publish-your-edge-server-topology"></a>Publicar sua topologia do Servidor de Borda

Depois que tiver concluído as etapas acima, é hora de publicar essa nova topologia, que também permitirá que você exportá-lo para seu Skype para pool de borda ou servidor de borda do servidor de negócios. Siga estas etapas:
  
1. Inicie o **Construtor de Topologia** (se ele já não foi iniciado no procedimento anterior).
    
2. No **Construtor de topologia**, na árvore de console, clique com o botão **Skype para Business Server** e clique em **Skype para o construtor de topologia de servidor de negócios**.
    
3. Na página **Bem-vindo** do assistente, clique em **Avançar**.
    
4. Na página **Criar outros bancos de dados**, clique em **Avançar**.
    
5. Quando o status indicar que a criação do banco de dados foi bem-sucedida, faça o seguinte:
    
    - Para exibir o log, clique em **Exibir log**.
    
    - Para fechar o assistente, clique em **Concluir**.
    
## <a name="export-your-edge-server-topology"></a>Exportar sua topologia do Servidor de Borda

Para implantar com êxito, o Skype para o Assistente de implantação do Business Server precisa acessar os dados do repositório de gerenciamento Central. Para servidores internos no seu domínio ou floresta, isso normalmente é bem direto. Servidores de borda estão fora do domínio e, portanto, é necessário exportar manualmente o arquivo de topologia para o local do servidor de borda, geralmente em uma mídia física. Esta exportação é feita via PowerShell:
  
1. Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.
    
2. No **Skype para Business Server Management Shell**, execute o seguinte:
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copie o arquivo exportado na mídia externa (por exemplo, um USB unidade ou compartilhamento de rede que pode ser acessada a partir de localização do servidor de borda).
    

