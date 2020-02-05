---
title: Criar sua topologia de borda para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumo: saiba como criar, publicar e exportar a topologia do servidor de borda no Skype for Business Server.'
ms.openlocfilehash: 3abde687899f240174e91d2583321bcdc6855fff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768324"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Criar sua topologia de borda para o Skype for Business Server
 
**Resumo:** Saiba como criar, publicar e exportar a topologia do servidor de borda no Skype for Business Server.
  
O construtor de topologias é a ferramenta que você precisa usar para criar a topologia do servidor de borda, da mesma forma que é usada para qualquer componente de topologia do Skype for Business Server. Antes de seguir as etapas abaixo, você precisará configurar pelo menos um pool de front-end ou um servidor Standard Edition.
  
Neste artigo, abordamos os seguintes tópicos:
  
- Criar a topologia do servidor de borda
    
- Publicar sua topologia do Servidor de Borda
    
- Exportar sua topologia do Servidor de Borda
    
  > [!NOTE]
  > Para seguir as etapas abaixo, você precisará se registrar nos servidores de domínio mencionados abaixo como um usuário que é membro dos seguintes grupos de domínio: 
  
- RTCUniversalServerAdmins
    
- Admins. do Domínio
    
## <a name="build-your-edge-server-topology"></a>Criar a topologia do servidor de borda

A primeira etapa de implantação é a criação da topologia do servidor de borda do Skype for Business Server, que consiste em uma das três opções:
  
- Um único servidor de borda
    
- Um pool de bordas com carga balanceada de DNS (um ou mais servidores)
    
- Um pool de bordas com carga balanceada de hardware (um ou mais servidores)
    
Se você não souber com certeza do que precisa, é uma boa hora para consultar a documentação de Planejamento antes de começar a seguir estas etapas. Caso contrário, vamos começar.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definindo a topologia para um servidor de borda único

1. Faça logon no servidor do Skype for Business Server Standard Edition ou em um pool de front-end do Skype for Business Server.
    
2. Depois disso, abra o **Construtor de topologias do Skype for Business Server**.
    
3. Na árvore de console, expanda o site para o qual você vai implantar o servidor de borda.
    
4. Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.
    
5. Clique em **Avançar** na tela **definir novo pool de borda** .
    
6. Na tela **definir o FQDN do pool de bordas** , digite o nome de domínio totalmente qualificado (FQDN) que o servidor de borda usará e selecione **pool de computador único**e clique **em Avançar** quando terminar.
    
7. Na tela **Selecionar recursos**, você tem uma escolha:
    
   - Você pode usar o mesmo FQDN e endereço IP para o seu serviço de acesso SIP, seu serviço de Webconferência do Skype for Business Server e seu serviço de borda A/V. Se esse for o caso, você deve marcar a caixa de seleção **Use um único FQDN e endereço IP** (e lembre-se disso na Etapa 9 abaixo)
    
   - Se você planejar habilitar a federação, marque a caixa de seleção **Habilitar federação para este servidor de Borda (porta 5061)**.
    
8. Depois de clicar em **Próximo**, você chegará na tela **Opções de IP**. Suas opções são:
    
   - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
   Esses são bem auto-explicativos, não importa se você está usando endereços IPv4 ou IPv6, e você está aplicando esses endereços em seu servidor de borda interna ou externamente (você precisará ter isso em mente para a etapa 10). Você também tem a opção de configurar o servidor de borda ou o pool de bordas para usar um endereço de NAT (conversão de endereços de rede) para o endereço IP externo. Você pode fazer isso marcando a caixa de seleção **O endereço IP externo deste pool de Borda é convertido pelo NAT**. Clique em **Avançar** quando estiver pronto.
    
9. Na tela de FQDNs Externos, suas opções dependem da seleção feita na Etapa 7 acima.
    
   - Se tiver marcado a caixa de seleção **usar um único FQDN e endereço IP** , você precisará inserir seu único FQDN externo na caixa de **acesso SIP** . Em seguida, você precisará inserir números de porta diferentes para cada serviço de borda para permitir que todos se conectem de forma independente. Recomendamos 5061 para o serviço de Borda de **Acesso SIP**, 444 para o serviço de Borda de **Webconferência** e 443 para o serviço de Borda **A/V**. Clique em **Avançar** quando terminar.
    
   - Se você não tiver verificado a caixa de seleção **usar um único FQDN e endereço IP** , agora precisará inserir os três FQDNs externos para o serviço de borda de **acesso SIP** , o serviço de borda de **Webconferência** e o serviço **de borda a/V** . Clique em **Avançar** quando terminar.
    
10. Agora você está na tela **definir o endereço IP interno** . Aqui você digitará o endereço IP do servidor de borda nas caixas de texto **endereço IPv4 interno** e **endereço IPv6 interno** , dependendo das opções feitas novamente na etapa 8. Clique em **Avançar** quando terminar.
    
11. Na tela **Definir o endereço IP externo**, você tem algumas opções dependendo de suas escolhas anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmativo, digite seu endereço IPv4 ou IPv6 externo (o que você estiver usando) na caixa de texto do **acesso SIP** e clique em **Avançar**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se esse for o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de borda de **acesso SIP** , o serviço de borda de **Webconferência** e o serviço **de borda a/V** e clique em **Avançar**.
    
    > [!NOTE]
    > Se você não escolheu habilitar e atribuir endereços IPv6 anteriormente, você não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
12. Se você optou por usar o NAT de volta na etapa 8, agora obterá uma tela com uma caixa de texto de **endereço IP público** . Você precisará inserir o endereço IPv4 e/ou IPv6 público que você definiu para o serviço de borda a/V, a ser traduzido por NAT. Clique em **Avançar**.
    
13. A próxima tela é **Definir o próximo salto**. Na caixa **próximo pool de saltos** , selecione o nome do seu pool interno, que pode ser um pool de front-ends ou um pool autônomo. Se você tiver um diretor em seu ambiente, deverá escolher o diretor. Then click **Next**.
    
14. Na tela **associar pools de front-end** , você precisará especificar um ou mais pools internos, incluindo pools front-end e servidores Standard Edition, para associar a este servidor de borda. Basta escolher os nomes dos pools internos que você deseja usar esse servidor de borda para se comunicar com usuários externos com suporte. Click **Next**.
    
    > [!NOTE]
    > Algo a ser lembrado aqui é, se seus pools internos ou autônomos já estiverem usando um servidor de borda diferente do Skype for Business Server, eles não poderão ter várias associações. Se você escolher um pool interno ou um servidor autônomo que está nessa situação, verá que um aviso será exibido informando sobre o outro servidor de borda e poderá decidir se deseja continuar ou não. Se você prosseguir com essa nova associação, a conexão com o outro Servidor de Borda será interrompida. 
  
15. Clique em **Concluir** na próxima tela.
    
16. Agora, você poderá publicar essa tecnologia atualizada e seguir as instruções em [implantar servidores de borda no Skype for Business Server](deploy-edge-servers.md) para implantar no servidor de borda aqui.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definindo a topologia de um pool de servidores de borda com balanceamento de carga de DNS

1. Faça logon no servidor do Skype for Business Server Standard Edition ou em um servidor front-end do Skype for Business Server.
    
2. Depois disso, abra o **Construtor de topologias do Skype for Business Server**.
    
3. Na árvore de console, expanda o site para o qual você vai implantar o servidor de borda.
    
4. Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.
    
5. Clique em **Avançar** na tela **definir novo pool de borda** .
    
6. Na tela **definir o FQDN do pool de bordas** , digite o nome de domínio totalmente qualificado (FQDN) que o pool de bordas usará e selecione **vários pools de computadores**e clique **em Avançar** quando terminar.
    
7. Na tela **Selecionar recursos**, você tem uma escolha:
    
    - Você pode usar o mesmo FQDN e endereço IP para o seu serviço de acesso SIP, seu serviço de Webconferência do Skype for Business Server e seu serviço de borda A/V. Se esse for o caso, você deve marcar a caixa de seleção **Use um único FQDN e endereço IP** (e lembre-se disso na Etapa 9 abaixo)
    
    - Se você planejar habilitar a federação, marque a caixa de seleção **Habilitar federação para este servidor de Borda (porta 5061)**.
    
8. Depois de clicar em **Próximo**, você chegará na tela **Opções de IP**. Suas opções são:
    
    - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
     Esses são bem auto-explicativos, não importa se você está usando endereços IPv4 ou IPv6, e você está aplicando esses endereços em seu servidor de borda interna ou externamente (você precisará ter isso em mente para a etapa 11). Você também tem a opção de configurar o servidor de borda ou o pool de bordas para usar um endereço de NAT (conversão de endereços de rede) para o endereço IP externo. Você pode fazer isso marcando a caixa de seleção **O endereço IP externo deste pool de Borda é convertido pelo NAT**. Clique em **Avançar** quando estiver pronto.
    
9. Na tela de FQDNs Externos, suas opções dependem da seleção feita na Etapa 7 acima.
    
   - Se tiver marcado a caixa de seleção **usar um único FQDN e endereço IP** , você precisará inserir seu único FQDN externo na caixa de **acesso SIP** . Em seguida, você precisará inserir números de porta diferentes para cada serviço de borda para permitir que todos se conectem de forma independente. Recomendamos 5061 para o serviço de Borda de **Acesso SIP**, 444 para o serviço de Borda de **Webconferência** e 443 para o serviço de Borda **A/V**. Clique em **Avançar** quando terminar.
    
   - Se você não tiver verificado a caixa de seleção **usar um único FQDN e endereço IP** , agora precisará inserir os três FQDNs externos para o serviço de borda de **acesso SIP** , o serviço de borda de **Webconferência** e o serviço **de borda a/V** . Clique em **Avançar** quando terminar.
    
10. Agora você atingiu a tela **definir os computadores neste pool** . Clique no botão **Adicionar**.
    
11. Agora você está na tela **definir o endereço IP interno** . Aqui você digitará o endereço IP do servidor de borda nas caixas de texto **endereço IPv4 interno** e **endereço IPv6 interno** , dependendo das opções feitas novamente na etapa 8. Clique em **Avançar** quando terminar.
    
12. Na tela **Definir o endereço IP externo**, você tem algumas opções dependendo de suas escolhas anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmativo, digite seu endereço IPv4 ou IPv6 externo (o que você estiver usando) na caixa de texto do **acesso SIP** e clique em **Avançar**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se esse for o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de borda de **acesso SIP** , o serviço de borda de **Webconferência** e o serviço **de borda a/V** e clique em **Avançar**.
    
    > [!NOTE]
    > Se você não escolheu habilitar e atribuir endereços IPv6 anteriormente, você não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
13. Clique em **Concluir**. O servidor de borda que você acabou de criar agora deve estar listado na caixa de diálogo **definir os computadores neste pool** .
    
14. Ainda na tela **definir os computadores neste pool** , clique no botão **Adicionar** novamente e repita as etapas de 11 a 13 até adicionar todos os servidores de borda que você pretende ter nesse pool. Quando terminar, clique em **Avançar**.
    
15. Se você optou por usar o NAT de volta na etapa 8, agora obterá uma tela com uma caixa de texto de **endereço IP público** . Você precisará inserir o endereço IPv4 e/ou IPv6 público que você definiu para o serviço de borda a/V, a ser traduzido por NAT. Clique em **Avançar**.
    
16. A próxima tela é **Definir o próximo salto**. Na caixa **próximo pool de saltos** , selecione o nome do seu pool interno, que pode ser um pool de front-ends ou um pool autônomo. Se você tiver um diretor em seu ambiente, deverá escolher o diretor. Then click **Next**.
    
17. Na tela **associar pools de front-end** , você precisará especificar um ou mais pools internos, incluindo pools de front-end e pools do Standard Edition, para associar a este servidor de borda. Basta escolher os nomes dos pools internos que você deseja usar esse servidor de borda para se comunicar com usuários externos com suporte. Click **Next**.
    
    > [!NOTE]
    > Algo a ser lembrado aqui é, se seus pools internos ou autônomos já estiverem usando um servidor de borda diferente do Skype for Business Server, eles não poderão ter várias associações. Se você escolher um pool interno ou um servidor autônomo que está nessa situação, verá que um aviso será exibido informando sobre o outro servidor de borda e poderá decidir se deseja continuar ou não. Se você prosseguir com essa nova associação, a conexão com o outro Servidor de Borda será interrompida. 
  
18. Clique em **Concluir** na próxima tela.
    
19. Agora, você poderá publicar essa tecnologia atualizada e seguir as instruções em [implantar servidores de borda no Skype for Business Server](deploy-edge-servers.md) para implantar no servidor de borda aqui.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definindo a topologia de um pool de servidores de borda com carga balanceada de hardware

1. Faça logon no servidor do Skype for Business Server Standard Edition ou em um servidor front-end do Skype for Business Server.
    
2. Depois disso, abra o **Construtor de topologias do Skype for Business Server**.
    
3. Na árvore de console, expanda o site para o qual você vai implantar o servidor de borda.
    
4. Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.
    
5. Clique em **Avançar** na tela **definir novo pool de borda** .
    
6. Na tela **definir o FQDN do pool de bordas** , digite o nome de domínio totalmente qualificado (FQDN) que o pool de bordas usará e selecione **vários pools de computadores**e clique **em Avançar** quando terminar.
    
7. Na tela **Selecionar recursos**, você tem uma escolha:
    
   - Você pode usar o mesmo FQDN e endereço IP para o seu serviço de acesso SIP, seu serviço de Webconferência do Skype for Business Server e seu serviço de borda A/V. Se esse for o caso, você deve marcar a caixa de seleção **Use um único FQDN e endereço IP** (e lembre-se disso na Etapa 9 abaixo)
    
   - Se você planejar habilitar a federação, marque a caixa de seleção **Habilitar federação para este servidor de Borda (porta 5061)**.
    
8. Depois de clicar em **Próximo**, você chegará na tela **Opções de IP**. Suas opções são:
    
   - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
     Esses são bem auto-explicativos, não importa se você está usando endereços IPv4 ou IPv6, e você está aplicando esses endereços em seu servidor de borda interna ou externamente (você precisará ter isso em mente para a etapa 11).
    
     > [!NOTE]
     > Ao contrário das outras duas opções de topologia, ao usar um balanceador de carga de hardware, você **não deve** selecionar a opção **o endereço IP externo do pool de bordas é traduzido por Nat**. Essa opção **não é suportada**.
  
9. Na tela de FQDNs Externos, suas opções dependem da seleção feita na Etapa 7 acima.
    
   - Se tiver marcado a caixa de seleção **usar um único FQDN e endereço IP** , você precisará inserir seu único FQDN externo na caixa de **acesso SIP** . Em seguida, você precisará inserir números de porta diferentes para cada serviço de borda para permitir que todos se conectem de forma independente. Recomendamos 5061 para o serviço de Borda de **Acesso SIP**, 444 para o serviço de Borda de **Webconferência** e 443 para o serviço de Borda **A/V**. Clique em **Avançar** quando terminar.
    
   - Se você não tiver verificado a caixa de seleção **usar um único FQDN e endereço IP** , agora precisará inserir os três FQDNs externos para o serviço de borda de **acesso SIP** , o serviço de borda de **Webconferência** e o serviço **de borda a/V** . Clique em **Avançar** quando terminar.
    
10. Agora você atingiu a tela **definir os computadores neste pool** . Clique no botão **Adicionar**.
    
11. Agora você está na tela **definir o endereço IP interno** . Aqui você digitará o endereço IP do servidor de borda nas caixas de texto **endereço IPv4 interno** e **endereço IPv6 interno** , dependendo das opções feitas novamente na etapa 8. Clique em **Avançar** quando terminar.
    
12. Na tela **Definir o endereço IP externo**, você tem algumas opções dependendo de suas escolhas anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmativo, digite seu endereço IPv4 ou IPv6 externo (o que você estiver usando) na caixa de texto do **acesso SIP** e clique em **Avançar**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se esse for o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de borda de **acesso SIP** , o serviço de borda de **Webconferência** e o serviço **de borda a/V** e clique em **Avançar**.
    
    > [!NOTE]
    > Se você não escolheu habilitar e atribuir endereços IPv6 anteriormente, você não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
13. Clique em **Concluir**. O servidor de borda que você acabou de criar agora deve estar listado na caixa de diálogo **definir os computadores neste pool** .
    
14. Ainda na tela **definir os computadores neste pool** , clique no botão **Adicionar** novamente e repita as etapas de 11 a 13 até adicionar todos os servidores de borda que você pretende ter nesse pool. Quando terminar, clique em **Avançar**.
    
15. A próxima tela é **Definir o próximo salto**. Na caixa **próximo pool de saltos** , selecione o nome do seu pool interno, que pode ser um pool de front-ends ou um pool autônomo. Se você tiver um diretor em seu ambiente, deverá escolher o diretor. Then click **Next**.
    
16. Na tela **associar pools de front-end** , você precisará especificar um ou mais pools internos, incluindo pools de front-end e pools do Standard Edition, para associar a este servidor de borda. Basta escolher os nomes dos pools internos que você deseja usar esse servidor de borda para se comunicar com usuários externos com suporte. Click **Next**.
    
    > [!NOTE]
    > Algo a ser lembrado aqui é, se seus pools internos ou autônomos já estiverem usando um servidor de borda diferente do Skype for Business Server, eles não poderão ter várias associações. Se você escolher um pool interno ou um servidor autônomo que está nessa situação, verá que um aviso será exibido informando sobre o outro servidor de borda e poderá decidir se deseja continuar ou não. Se você prosseguir com essa nova associação, a conexão com o outro Servidor de Borda será interrompida. 
  
17. Clique em **Concluir** na próxima tela.
    
18. Agora, você poderá publicar essa tecnologia atualizada e seguir as instruções em [implantar servidores de borda no Skype for Business Server](deploy-edge-servers.md) para implantar no servidor de borda aqui.
    
## <a name="publish-your-edge-server-topology"></a>Publicar sua topologia do Servidor de Borda

Depois de concluir as etapas acima, é hora de publicar essa nova topologia, o que também permitirá que você a exporte para o seu servidor de borda do Skype for Business Server ou para o pool de bordas. Siga estas etapas:
  
1. Inicie o **Construtor de Topologia** (se ele já não foi iniciado no procedimento anterior).
    
2. No **Construtor de topologias**, na árvore de console, clique com o botão direito do mouse em **Skype for Business Server** e clique em **Construtor de topologia do Skype for Business Server**.
    
3. Na página **Bem-vindo** do assistente, clique em **Avançar**.
    
4. Na página **Criar outros bancos de dados**, clique em **Avançar**.
    
5. Quando o status indicar que a criação do banco de dados foi bem-sucedida, faça o seguinte:
    
    - Para exibir o log, clique em **Exibir log**.
    
    - Para fechar o assistente, clique em **Concluir**.
    
## <a name="export-your-edge-server-topology"></a>Exportar sua topologia do Servidor de Borda

Para implantar com êxito, o assistente de implantação do Skype for Business Server precisa acessar os dados do repositório de gerenciamento central. Para servidores internos no seu domínio ou floresta, isso normalmente é bem direto. Os servidores de borda estão fora do domínio e, portanto, é necessário exportar manualmente o arquivo de topologia para o local do servidor de borda, geralmente em uma mídia física. Esta exportação é feita via PowerShell:
  
1. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
2. No **Shell de gerenciamento do Skype for Business Server**, execute o seguinte:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copie o arquivo exportado para mídia externa (por exemplo, uma unidade USB ou um compartilhamento de rede que você possa alcançar na localização do servidor de borda).
    

