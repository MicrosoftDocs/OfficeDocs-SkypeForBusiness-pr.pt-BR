---
title: Implantar um servidor de mediação no construtor de topologia no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumo: Saiba como definir e implantar um servidor de mediação no construtor de topologia no Skype para Business Server.'
ms.openlocfilehash: 5e4221230fbaf993b5bf3d2b647e6d7e6e7ada51
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371918"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Implantar um servidor de mediação no construtor de topologia no Skype para Business Server
 
**Resumo:** Saiba como definir e implantar um servidor de mediação no construtor de topologia no Skype para Business Server.
  
A carga de trabalho do Enterprise Voice, conferência discada e aplicativos avançados do Enterprise Voice (aplicativo grupo de resposta, o aplicativo de estacionamento de chamada, o controle de admissão de chamadas (CAC) e assim por diante), estão disponíveis nos pools de Front-End. A funcionalidade do servidor de mediação é inserida no servidor Front-End. Um servidor de mediação autônomo separado não é necessário. 
  
A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet. Para conectar sua infraestrutura do Enterprise Voice com seu provedor de tronco SIP, um servidor de mediação separado deve ser implantado.
  
A conexão entre Skype para Business Server (qualquer um servidor de mediação colocado em um pool de Front-End ou servidor de mediação autônomo) e um gateway é definido como uma associação lógica chamada um tronco. Os tópicos desta seção descrevem como definir um tronco e como implantar um servidor de mediação autônomo, se você conectar a um tronco SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definir um Servidor de Mediação no Construtor de Topologia

Você pode adicionar o servidor de mediação como uma função colocada em um pool de Front-End ou definir um pool do servidor de mediação de autônomo separado.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para adicionar um servidor de mediação para um pool de Front-End

1. Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.
    
2. No construtor de topologia, na árvore de console, expanda o nome do site para o qual você deseja definir um pool de Front-End.
    
3. Na árvore de console, clique com botão direito do tipo de pool de Front-End que você deseja e clique em **pool de Front-End novo …**.
    
4. Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.
    
5. Nas **funções de servidor colocadas Select**, marque a opção **Colocar o servidor de mediação**.
    
    > [!NOTE]
    > Se o tipo de pool de Front-End que você selecionou for o Enterprise Edition, em seguida, o componente de servidor de mediação será instalado em todos os servidores Front-End desse pool de Front-End. 
  
    > [!NOTE]
    > O **pool de próximo salto** usado pelo servidor de mediação será o pool de Front-End, qual o servidor de mediação é colocado.
  
    > [!NOTE]
    > O **pool de borda** usado pelo servidor de mediação será o mesmo pool de borda associado ao pool de Front-End no qual o servidor de mediação é colocado.
  
6. Clique em **Tornar padrão** para usar este pool de Front-End para rotear chamadas para a PSTN.
    
7. Clique em **Concluir** quando tiver terminado de associar um ou mais pares ao pool de Front-End.
    
    > [!NOTE]
    > Antes de prosseguir para a próxima etapa do processo de implantação do Enterprise Voice, certifique-se de que o pool de servidor de mediação (isto é, Front End pool com o componente de servidor de mediação colocado) está usando os FQDNs que você especificou. 
  
8. Com o botão direito no nó do **Skype para Business Server 2015** e, em seguida, clique em **Publicar topologia**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Para adicionar um Servidor de Mediação autônomo

1. Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.
    
2. No construtor de topologia, na árvore de console, expanda o nome do site para o qual você deseja definir um servidor de mediação.
    
3. Na árvore de console, clique com botão direito no nó **pools de mediação** e clique em **pool de servidor de mediação**.
    
4. Em **Definir Novo Pool de mediação**, digite o nome de domínio totalmente qualificado do pool do servidor de mediação (FQDN).
    
5. Em seguida, siga um destes procedimentos:
    
   - Se desejar implantar vários servidores de mediação no pool para fornecer alta disponibilidade, selecione **pool de vários computadores**.
    
     > [!NOTE]
     > Você deve [implantar](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para oferecer suporte a pools de servidor de mediação que possuem vários servidores de mediação.
  
   - Se você deseja implantar apenas um servidor de mediação no pool, porque você não requerem alta disponibilidade, selecione **pool de computador único**. Ignore a etapa seguinte.
    
6. Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**. Repita essa etapa para todos os outros servidores de mediação que você deseja adicionar ao pool. Quando tiver definido todos os computadores no pool, clique em **Avançar**.
    
7. Na página **Selecionar o próximo salto** , clique em **pool de próximo salto**, o FQDN do pool Front-Ends que usará esse pool de servidores de mediação e clique em **Avançar**.
    
8. Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:
    
   - Se você deseja oferecer conectividade PSTN para usuários externos habilitados para o Enterprise Voice, em **Selecione Pool de borda usado pelo servidor de mediação**, clique em FQDN do pool de servidores de borda que usará esse pool de servidores de mediação para fornecer conectividade PSTN para os usuários externos e, em seguida, clique em **Avançar**.
    
   - Se você não planeja permitir que usuários externos para o Enterprise Voice, ou se você não deseja fornecer conectividade PSTN para usuários quando eles estão fora da rede interna, clique em **Avançar**.
    
9. Com o botão direito no nó do **Skype para Business Server 2015** e, em seguida, clique em **Publicar topologia**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definir as portas de escuta do servidor de mediação

Siga as etapas neste tópico para usar o construtor de topologias para definir as portas de escuta um servidor de mediação ou pool aceitará conexões de entrada de um par de gateway.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar as portas de escuta do servidor de mediação

1. Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.
    
2. No construtor de topologia, na árvore de console, expanda o nó **pools de mediação** e clique com o botão o servidor de mediação criado anteriormente.
    
3. Por padrão, as portas de escuta SIP no servidor de mediação são 5070 tráfego TLS nos Skype para Business Server e 5067 tráfego TLS nos peers (por exemplo, gateways, PBXs ou SBCs). A porta TCP é desabilitada por padrão. Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.
    
4. Especifique o desejada TLS ou TCP escutando intervalo de porta do servidor de mediação aceitará conexões de entrada de gateways PSTN.
    
    > [!NOTE]
    > Não é necessário inserir um intervalo de portas TCP se a opção **Habilitar porta TCP** não estiver marcada. Essa configuração é opcional.
  

