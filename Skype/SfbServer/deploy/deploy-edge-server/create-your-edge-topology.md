---
title: Crie sua topologia de borda para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Resumo: saiba como criar, publicar e exportar sua topologia do Servidor de Borda em Skype for Business Server.'
ms.openlocfilehash: ff7c2e69c3ee18da5c798fbdf96719bd14146d45
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775801"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Crie sua topologia de borda para Skype for Business Server
 
**Resumo:** Saiba como criar, publicar e exportar sua topologia do Servidor de Borda em Skype for Business Server.
  
O Construtor de Topologias é a ferramenta que você precisa usar para criar sua topologia do Servidor de Borda, assim como é usada para qualquer componente de topologia para Skype for Business Server. Antes de seguir as etapas abaixo, você precisará configurar pelo menos um pool de Front-End ou um Edição Standard servidor.
  
Abrangemos os seguintes tópicos neste artigo:
  
- Criar sua topologia do Servidor de Borda
    
- Publicar sua topologia do Servidor de Borda
    
- Exportar sua topologia do Servidor de Borda
    
  > [!NOTE]
  > Para seguir as etapas abaixo, você precisará fazer logoff nos servidores de domínio mencionados abaixo como um usuário membro dos seguintes grupos de domínio: 
  
- RTCUniversalServerAdmins
    
- Admins de domínio
    
## <a name="build-your-edge-server-topology"></a>Criar sua topologia do Servidor de Borda

A primeira etapa de implantação é criar Skype for Business Server topologia do Servidor de Borda, que consiste em uma das três opções:
  
- Um único Servidor de Borda
    
- Um pool de Borda balanceado de carga DNS (um ou mais servidores)
    
- Um pool de Borda balanceado de carga de hardware (um ou mais servidores)
    
Se você não tiver certeza do que precisa, antes de começar a seguir essas etapas, é uma boa hora para ver a documentação de Planejamento. Caso contrário, vamos começar.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definindo a topologia de um único Servidor de Borda

1. Faça logoff no servidor Skype for Business Server Edição Standard ou em um pool Skype for Business Server front-end.
    
2. Uma vez lá, abra **Skype for Business Server Construtor de Topologias.**
    
3. Na árvore de console, expanda o site para o onde você implantará o Servidor de Borda.
    
4. Clique com o botão direito do mouse em **Pools de** Borda e clique em **Novo Pool de Borda.**
    
5. Você clicará em **Next** na tela **Definir Novo Pool de** Borda.
    
6. Na tela Definir o **FQDN** do pool de Borda, digite o FQDN (nome de domínio totalmente qualificado) interno que o Servidor de Borda usará e selecione Pool de computador **único**, clicando em **Next** quando terminar.
    
7. Na tela **Selecionar recursos,** você tem uma opção:
    
   - Talvez você pretenda usar o mesmo FQDN e endereço IP para seu serviço de Acesso SIP, seu serviço Skype for Business Server WebConferência e seu serviço de Borda A/V. Nesse caso, você precisa escolher a caixa de seleção Usar um único **FQDN** e endereço IP (e ter isso em mente para a Etapa 9 abaixo)
    
   - Se você estiver planejando habilitar a federação, escolha a caixa de seleção Habilitar federação para este pool de Borda **(Porta 5061).**
    
8. Depois de clicar em **Next,** você se encontrará na tela Opções **de IP.** Suas opções são as seguinte:
    
   - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
   Eles são bastante autoexplicativos, seja você usando endereços IPv4 ou IPv6, e você está aplicando esses endereços em seu Servidor de Borda interna ou externamente (você precisará ter isso em mente para a Etapa 10). Você também tem a opção de configurar seu Servidor de Borda ou seu pool de Borda para usar um endereço NAT (conversão de endereço de rede) para o endereço IP externo. Você pode fazer isso escolhendo O endereço **IP externo deste pool** de Borda é convertido pela caixa de seleção NAT . Clique **em Próximo** quando estiver pronto.
    
9. Na tela FQDNs externos, suas escolhas dependem da seleção feita na Etapa 7 acima.
    
   - Se você marcou a caixa de seleção Usar um único **FQDN** e Endereço IP, você precisará inserir seu FQDN externo único na caixa **Acesso SIP.** Em seguida, você precisará inserir números de porta diferentes para cada serviço de borda para permitir que todos eles se conectem independentemente. Recomendamos o 5061 para o serviço de Borda de Acesso **SIP,** 444 para o serviço de Borda de **WebConferência** e 443 para o serviço de Borda **A/V.** Quando terminar, escolha **Avançar**.
    
   - Se você não tiver marcado a caixa de seleção Usar um único **FQDN** e Endereço IP, agora precisará inserir os três FQDNs externos para o serviço de Borda de Acesso **SIP,** o serviço de Borda de **WebConferência** e o serviço de Borda **A/V.** Quando terminar, escolha **Avançar**.
    
10. Agora você está na tela **Definir o endereço IP** interno. Aqui, você digitará o endereço IP do servidor de borda nas caixas de texto **IPv4** internas e **IPv6** internas, dependendo das escolhas feitas na Etapa 8. Clique **em Próximo** quando estiver pronto.
    
11. Na tela **Definir o endereço IP** externo, você tem algumas opções, dependendo das opções anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmado, digite seu endereço IPv4 ou IPv6 externo (o que você estiver usando) na caixa de texto **Acesso SIP** e clique em **Próximo**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se esse for o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de Borda de Acesso **SIP,** o serviço de Borda de **WebConferência** e o serviço de Borda **A/V** e clique em **Próximo**.
    
    > [!NOTE]
    > Se você não tiver optado anteriormente por habilitar e atribuir endereçamento IPv6, não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
12. Se você optou por usar NAT novamente na Etapa 8, agora você obterá uma tela com uma caixa de **texto de endereço IP** público. Você precisará inserir o endereço IPv4 e/ou IPv6 público que você definiu para o serviço de Borda A/V, a ser convertido pelo NAT. Depois, clique em **Avançar**.
    
13. A próxima tela para cima **é Definir o próximo salto**. Na caixa **Pool de próximo salto,** selecione o nome do pool interno, que pode ser um pool front-end ou um pool autônomo. Se você tiver um Diretor em seu ambiente, escolha o Diretor. Depois, clique em **Avançar**.
    
14. Na tela **Associar pools front-end,** você precisará especificar um ou mais pools internos, incluindo pools de front-end e servidores Edição Standard, para associar a esse Servidor de Borda. Basta escolher os nomes dos pools internos que você deseja usar esse Servidor de Borda para se comunicar com usuários externos com suporte. Clique em **Avançar**.
    
    > [!NOTE]
    > Algo para ter em mente aqui é que, se seus pools internos ou servidores autônomo Skype for Business Server s já estão usando um servidor de borda diferente, eles não podem ter várias associações. Se você escolher um pool interno ou um servidor autônomo que está nessa situação, você verá um aviso aparecer avisando sobre o outro Servidor de Borda e poderá decidir se deseja continuar ou não. Se você continuar com essa nova associação, a conexão com o outro Servidor de Borda será parada. 
  
15. Clique **em Concluir** na próxima tela.
    
16. Agora você poderá publicar essa tecnologia atualizada e seguir as instruções em [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) deploy to your Edge Server from here.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definindo a topologia de um pool de Servidor de Borda balanceado de carga DNS

1. Faça logoff no Skype for Business Server Edição Standard servidor ou em um servidor Skype for Business Server front-end.
    
2. Uma vez lá, abra **Skype for Business Server Construtor de Topologias.**
    
3. Na árvore de console, expanda o site para o onde você implantará o Servidor de Borda.
    
4. Clique com o botão direito do mouse em **Pools de** Borda e clique em **Novo Pool de Borda.**
    
5. Você clicará em **Next** na tela **Definir Novo Pool de** Borda.
    
6. Na tela Definir o **FQDN** do pool de Borda, digite o FQDN (nome de domínio totalmente qualificado) interno que o pool de Borda usará e selecione Pool de vários computadores **,** clicando em **Next** quando terminar.
    
7. Na tela **Selecionar recursos,** você tem uma opção:
    
    - Talvez você pretenda usar o mesmo FQDN e endereço IP para seu serviço de Acesso SIP, seu serviço Skype for Business Server WebConferência e seu serviço de Borda A/V. Nesse caso, você precisa escolher a caixa de seleção Usar um único **FQDN** e endereço IP (e ter isso em mente para a Etapa 9 abaixo)
    
    - Se você estiver planejando habilitar a federação, escolha a caixa de seleção Habilitar federação para este pool de Borda **(Porta 5061).**
    
8. Depois de clicar em **Next,** você se encontrará na tela Opções **de IP.** Suas opções são as seguinte:
    
    - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
     Eles são bastante autoexplicativos, seja você usando endereços IPv4 ou IPv6, e você está aplicando esses endereços em seu Servidor de Borda interna ou externamente (você precisará ter isso em mente para a Etapa 11). Você também tem a opção de configurar seu Servidor de Borda ou seu pool de Borda para usar um endereço NAT (conversão de endereço de rede) para o endereço IP externo. Você pode fazer isso escolhendo O endereço **IP externo deste pool** de Borda é convertido pela caixa de seleção NAT . Clique **em Próximo** quando estiver pronto.
    
9. Na tela FQDNs externos, suas escolhas dependem da seleção feita na Etapa 7 acima.
    
   - Se você marcou a caixa de seleção Usar um único **FQDN** e Endereço IP, você precisará inserir seu FQDN externo único na caixa **Acesso SIP.** Em seguida, você precisará inserir números de porta diferentes para cada serviço de borda para permitir que todos eles se conectem independentemente. Recomendamos o 5061 para o serviço de Borda de Acesso **SIP,** 444 para o serviço de Borda de **WebConferência** e 443 para o serviço de Borda **A/V.** Quando terminar, escolha **Avançar**.
    
   - Se você não tiver marcado a caixa de seleção Usar um único **FQDN** e Endereço IP, agora precisará inserir os três FQDNs externos para o serviço de Borda de Acesso **SIP,** o serviço de Borda de **WebConferência** e o serviço de Borda **A/V.** Quando terminar, escolha **Avançar**.
    
10. Agora você atingiu a tela **Definir os computadores nesta tela de** pool. Clique no botão **Adicionar**.
    
11. Agora você está na tela **Definir o endereço IP** interno. Aqui, você digitará o endereço IP do servidor de borda nas caixas de texto **IPv4** internas e **IPv6** internas, dependendo das escolhas feitas na Etapa 8. Clique **em Próximo** quando estiver pronto.
    
12. Na tela **Definir o endereço IP** externo, você tem algumas opções, dependendo das opções anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmado, digite seu endereço IPv4 ou IPv6 externo (o que você estiver usando) na caixa de texto **Acesso SIP** e clique em **Próximo**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se esse for o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de Borda de Acesso **SIP,** o serviço de Borda de **WebConferência** e o serviço de Borda **A/V** e clique em **Próximo**.
    
    > [!NOTE]
    > Se você não tiver optado anteriormente por habilitar e atribuir endereçamento IPv6, não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
13. Clique em **Concluir**. O Servidor de Borda que você acabou de criar agora deve estar listado na caixa de diálogo **Definir os computadores neste pool.**
    
14. Enquanto ainda estiver na tela Definir os  computadores neste **pool,** clique no botão Adicionar novamente e repita as etapas de 11 a 13 até adicionar todos os Servidores de Borda que você pretende ter neste pool. Quando isso for concluído, clique em **Próximo**.
    
15. Se você optou por usar NAT novamente na Etapa 8, agora você obterá uma tela com uma caixa de **texto de endereço IP** público. Você precisará inserir o endereço IPv4 e/ou IPv6 público que você definiu para o serviço de Borda A/V, a ser convertido pelo NAT. Depois, clique em **Avançar**.
    
16. A próxima tela para cima **é Definir o próximo salto**. Na caixa **Pool de próximo salto,** selecione o nome do pool interno, que pode ser um pool front-end ou um pool autônomo. Se você tiver um Diretor em seu ambiente, escolha o Diretor. Depois, clique em **Avançar**.
    
17. Na tela **Associar pools front-end,** você precisará especificar um ou mais pools internos, incluindo pools de front-end e pools Edição Standard, para associar a esse Servidor de Borda. Basta escolher os nomes dos pools internos que você deseja usar esse Servidor de Borda para se comunicar com usuários externos com suporte. Clique em **Avançar**.
    
    > [!NOTE]
    > Algo para ter em mente aqui é que, se seus pools internos ou servidores autônomo Skype for Business Server s já estão usando um servidor de borda diferente, eles não podem ter várias associações. Se você escolher um pool interno ou um servidor autônomo que está nessa situação, você verá um aviso aparecer avisando sobre o outro Servidor de Borda e poderá decidir se deseja continuar ou não. Se você continuar com essa nova associação, a conexão com o outro Servidor de Borda será parada. 
  
18. Clique **em Concluir** na próxima tela.
    
19. Agora você poderá publicar essa tecnologia atualizada e seguir as instruções em [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) deploy to your Edge Server from here.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definindo a topologia de um pool de Servidor de Borda balanceado de carga de hardware

1. Faça logoff no Skype for Business Server Edição Standard servidor ou em um servidor Skype for Business Server front-end.
    
2. Uma vez lá, abra **Skype for Business Server Construtor de Topologias.**
    
3. Na árvore de console, expanda o site para o onde você implantará o Servidor de Borda.
    
4. Clique com o botão direito do mouse em **Pools de** Borda e clique em **Novo Pool de Borda.**
    
5. Você clicará em **Next** na tela **Definir Novo Pool de** Borda.
    
6. Na tela Definir o **FQDN** do pool de Borda, digite o FQDN (nome de domínio totalmente qualificado) interno que o pool de Borda usará e selecione Pool de vários computadores **,** clicando em **Next** quando terminar.
    
7. Na tela **Selecionar recursos,** você tem uma opção:
    
   - Talvez você pretenda usar o mesmo FQDN e endereço IP para seu serviço de Acesso SIP, seu serviço Skype for Business Server WebConferência e seu serviço de Borda A/V. Nesse caso, você precisa escolher a caixa de seleção Usar um único **FQDN** e endereço IP (e ter isso em mente para a Etapa 9 abaixo)
    
   - Se você estiver planejando habilitar a federação, escolha a caixa de seleção Habilitar federação para este pool de Borda **(Porta 5061).**
    
8. Depois de clicar em **Next,** você se encontrará na tela Opções **de IP.** Suas opções são as seguinte:
    
   - Habilitar IPv4 na interface interna
    
   - Habilitar IPv6 na interface interna
    
   - Habilitar IPv4 na interface externa
    
   - Habilitar IPv6 na interface externa
    
     Eles são bastante autoexplicativos, seja você usando endereços IPv4 ou IPv6, e você está aplicando esses endereços em seu Servidor de Borda interna ou externamente (você precisará ter isso em mente para a Etapa 11).
    
     > [!NOTE]
     > Diferentemente das outras duas opções de topologia, ao usar um balanceador de carga de hardware, você NÃO **DEVE** selecionar a opção O endereço IP externo do Pool de Borda é convertido **por NAT**. Não há **suporte para** isso.
  
9. Na tela FQDNs externos, suas escolhas dependem da seleção feita na Etapa 7 acima.
    
   - Se você marcou a caixa de seleção Usar um único **FQDN** e Endereço IP, você precisará inserir seu FQDN externo único na caixa **Acesso SIP.** Em seguida, você precisará inserir números de porta diferentes para cada serviço de borda para permitir que todos eles se conectem independentemente. Recomendamos o 5061 para o serviço de Borda de Acesso **SIP,** 444 para o serviço de Borda de **WebConferência** e 443 para o serviço de Borda **A/V.** Quando terminar, escolha **Avançar**.
    
   - Se você não tiver marcado a caixa de seleção Usar um único **FQDN** e Endereço IP, agora precisará inserir os três FQDNs externos para o serviço de Borda de Acesso **SIP,** o serviço de Borda de **WebConferência** e o serviço de Borda **A/V.** Quando terminar, escolha **Avançar**.
    
10. Agora você atingiu a tela **Definir os computadores nesta tela de** pool. Clique no botão **Adicionar**.
    
11. Agora você está na tela **Definir o endereço IP** interno. Aqui, você digitará o endereço IP do servidor de borda nas caixas de texto **IPv4** internas e **IPv6** internas, dependendo das escolhas feitas na Etapa 8. Clique **em Próximo** quando estiver pronto.
    
12. Na tela **Definir o endereço IP** externo, você tem algumas opções, dependendo das opções anteriores:
    
    - Você pode estar usando um único FQDN para todos os serviços. Em caso afirmado, digite seu endereço IPv4 ou IPv6 externo (o que você estiver usando) na caixa de texto **Acesso SIP** e clique em **Próximo**.
    
    - Você pode ter escolhido usar três FQDNs e endereços IP separados para os serviços. Se esse for o caso, insira seus endereços IPv4 ou IPv6 externos para o serviço de Borda de Acesso **SIP,** o serviço de Borda de **WebConferência** e o serviço de Borda **A/V** e clique em **Próximo**.
    
    > [!NOTE]
    > Se você não tiver optado anteriormente por habilitar e atribuir endereçamento IPv6, não verá essa caixa de diálogo. Isso é normal, basta ir para a próxima etapa. 
  
13. Clique em **Concluir**. O Servidor de Borda que você acabou de criar agora deve estar listado na caixa de diálogo **Definir os computadores neste pool.**
    
14. Enquanto ainda estiver na tela Definir os  computadores neste **pool,** clique no botão Adicionar novamente e repita as etapas de 11 a 13 até adicionar todos os Servidores de Borda que você pretende ter neste pool. Quando isso for concluído, clique em **Próximo**.
    
15. A próxima tela para cima **é Definir o próximo salto**. Na caixa **Pool de próximo salto,** selecione o nome do pool interno, que pode ser um pool front-end ou um pool autônomo. Se você tiver um Diretor em seu ambiente, escolha o Diretor. Depois, clique em **Avançar**.
    
16. Na tela **Associar pools front-end,** você precisará especificar um ou mais pools internos, incluindo pools de front-end e pools Edição Standard, para associar a esse Servidor de Borda. Basta escolher os nomes dos pools internos que você deseja usar esse Servidor de Borda para se comunicar com usuários externos com suporte. Clique em **Avançar**.
    
    > [!NOTE]
    > Algo para ter em mente aqui é que, se seus pools internos ou servidores autônomo Skype for Business Server s já estão usando um servidor de borda diferente, eles não podem ter várias associações. Se você escolher um pool interno ou um servidor autônomo que está nessa situação, você verá um aviso aparecer avisando sobre o outro Servidor de Borda e poderá decidir se deseja continuar ou não. Se você continuar com essa nova associação, a conexão com o outro Servidor de Borda será parada. 
  
17. Clique **em Concluir** na próxima tela.
    
18. Agora você poderá publicar essa tecnologia atualizada e seguir as instruções em [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) deploy to your Edge Server from here.
    
## <a name="publish-your-edge-server-topology"></a>Publicar sua topologia do Servidor de Borda

Depois de terminar as etapas acima, é hora de publicar essa nova topologia, que também permitirá que você exporte-a para seu servidor de borda ou pool de Borda Skype for Business Server de borda. Siga estas etapas:
  
1. Inicie **o Construtor de Topologias** (se ainda não tiver sido iniciado no procedimento anterior).
    
2. No **Construtor de Topologias,** na árvore do console, clique com o botão direito do **mouse Skype for Business Server** e clique Skype for Business Server Construtor **de Topologias.**
    
3. Na página **Bem-vindo** do assistente, clique em **Avançar**.
    
4. Na página **Criar outros bancos de dados**, clique em **Avançar**.
    
5. Quando o status indicar que a criação do banco de dados foi bem-sucedida, faça o seguinte:
    
    - Para exibir o log, clique em **Exibir log**.
    
    - Para fechar o assistente, clique em **Concluir**.
    
## <a name="export-your-edge-server-topology"></a>Exportar sua topologia do Servidor de Borda

Para implantar com êxito, o Assistente Skype for Business Server implantação precisa de acesso aos dados do armazenamento de Gerenciamento Central. Para servidores internos em seu domínio ou floresta, isso normalmente é simples. Os Servidores de Borda estão fora do domínio e, portanto, é necessário exportar manualmente o arquivo de topologia para o local do Servidor de Borda, geralmente em uma mídia física. Essa exportação é feita por meio do PowerShell:
  
1. Inicie o **Shell de Gerenciamento Skype for Business Server .**
    
2. No Shell **Skype for Business Server Gerenciamento**, execute o seguinte:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copie o arquivo exportado para mídia externa (por exemplo, uma unidade USB ou compartilhamento de rede que você pode alcançar a partir do local do Servidor de Borda).
    

