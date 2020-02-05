---
title: Implantar um servidor de mediação no construtor de topologias no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumo: saiba como definir e implantar um servidor de mediação no construtor de topologias no Skype for Business Server.'
ms.openlocfilehash: c651ff3e254165161642c4e729d0d4e3f2983023
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767684"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Implantar um servidor de mediação no construtor de topologias no Skype for Business Server
 
**Resumo:** Saiba como definir e implantar um servidor de mediação no construtor de topologias no Skype for Business Server.
  
A carga de trabalho do Enterprise Voice, a conferência discada e os aplicativos avançados do Enterprise Voice (aplicativo do grupo de resposta, o aplicativo de estacionamento de chamadas, o controle de admissão de chamadas (CAC) e assim por diante) estão disponíveis em pools front-ends. A funcionalidade do servidor de mediação está embutida no servidor front-end. Um servidor de mediação autônomo separado não é necessário. 
  
A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet. Para conectar sua infraestrutura do Enterprise Voice ao seu provedor de tronco SIP, um servidor de mediação separado deve ser implantado.
  
A conexão entre o Skype for Business Server (um servidor de mediação posicionado em um pool Front-end ou um servidor autônomo de mediação) e um gateway é definido como uma associação lógica chamada de tronco. Os tópicos desta seção descrevem como definir um tronco e como implantar um servidor de mediação autônomo, se você se conectar a um tronco SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definir um Servidor de Mediação no Construtor de Topologia

Você pode adicionar o servidor de mediação como uma função posicionada em um pool de front-end ou definir um pool separado do servidor de mediação autônomo.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para adicionar um servidor de mediação a um pool de front-ends

1. Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.
    
2. No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um pool de front-ends.
    
3. Na árvore do console, clique com o botão direito do mouse no tipo de pool de front-end desejado e, em seguida, clique em **novo pool de front-ends..**.
    
4. Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.
    
5. Em **selecionar funções de servidor posicionadas**, marque a opção **posicionar servidor de mediação**.
    
    > [!NOTE]
    > Se o tipo de pool de front-end selecionado for a edição Enterprise, o componente servidor de mediação será instalado em todos os servidores front-end desse pool de front-ends. 
  
    > [!NOTE]
    > O **próximo pool de saltos** usado pelo servidor de mediação será o pool de front-ends em que o servidor de mediação está posicionado.
  
    > [!NOTE]
    > O **pool de bordas** usado pelo servidor de mediação será o mesmo pool de bordas associado ao pool de front-ends em que o servidor de mediação está posicionado.
  
6. Clique em **criar padrão** para usar este pool de front-ends para direcionar chamadas para a PSTN.
    
7. Clique em **concluir** quando terminar de associar um ou mais pares ao pool de front-ends.
    
    > [!NOTE]
    > Antes de prosseguir para a próxima etapa no processo de implantação do Enterprise Voice, verifique se o pool do servidor de mediação (ou seja, o pool do front-end com o componente do servidor de mediação está posicionado) está usando os FQDNs que você especificou. 
  
8. Clique com o botão direito do mouse no nó do **Skype for Business Server 2015** e, em seguida, clique em **publicar topologia**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Para adicionar um Servidor de Mediação autônomo

1. Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.
    
2. No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um servidor de mediação.
    
3. Na árvore de console, clique com o botão direito do mouse no nó de **pools de mediação** e clique em **pool do servidor de mediação**.
    
4. Em **definir novo pool de mediação**, digite o nome de domínio totalmente qualificado (FQDN) do pool do servidor de mediação.
    
5. Em seguida, siga um destes procedimentos:
    
   - Se você quiser implantar vários servidores de mediação no pool para fornecer alta disponibilidade, selecione **vários pools de computadores**.
    
     > [!NOTE]
     > Você deve [implantar](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para dar suporte a pools do servidor de mediação que têm vários servidores de mediação.
  
   - Se você quiser implantar apenas um servidor de mediação no pool porque não requer alta disponibilidade, selecione um **único pool de computador**. Ignore a etapa seguinte.
    
6. Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**. Repita esta etapa para todos os outros servidores de mediação que você deseja adicionar ao pool. Quando tiver definido todos os computadores no pool, clique em **Avançar**.
    
7. Na página **selecionar o próximo salto** , clique em **próximo pool de saltos**, clique no FQDN do pool de front-ends que usará esse pool do servidor de mediação e, em seguida, clique em **Avançar**.
    
8. Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:
    
   - Se você quiser fornecer conectividade PSTN a usuários externos habilitados para o Enterprise Voice, em **Selecione o pool de bordas usado por esse servidor de mediação**, clique no FQDN do pool do servidor de borda que usará esse pool de servidores de mediação para fornecer conectividade PSTN a esses usuários externos e clique em **Avançar**.
    
   - Se você não planeja habilitar usuários externos para o Enterprise Voice ou se não quiser fornecer conectividade PSTN aos usuários quando eles estiverem fora da rede interna, clique em **Avançar**.
    
9. Clique com o botão direito do mouse no nó do **Skype for Business Server 2015** e, em seguida, clique em **publicar topologia**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definir as portas de escuta do servidor de mediação

Siga as etapas deste tópico para usar o construtor de topologias a fim de definir as portas de escuta que um servidor ou um pool de mediação aceitará conexões de entrada de um ponto de gateway.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar as portas de escuta do servidor de mediação

1. Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.
    
2. No construtor de topologias, na árvore de console, expanda o nó de **pools de mediação** e clique com o botão direito do mouse no servidor de mediação anteriormente criado.
    
3. Por padrão, as portas de escuta SIP no servidor de mediação são 5070 para tráfego TLS do Skype for Business Server e 5067 para tráfego TLS de pares (como gateways, PBXes ou SBCs). A porta TCP é desabilitada por padrão. Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.
    
4. Especificar o intervalo de portas de escuta de TLS ou TCP desejadas o servidor de mediação aceitará conexões de entrada de gateways PSTN.
    
    > [!NOTE]
    > Não é necessário inserir um intervalo de portas TCP se a opção **Habilitar porta TCP** não estiver marcada. Essa configuração é opcional.
  

