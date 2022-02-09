---
title: Implantar um Servidor de Mediação no Construtor de Topologias Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumo: saiba como definir e implantar um Servidor de Mediação no Construtor de Topologias Skype for Business Server.'
ms.openlocfilehash: 1e7f3b1540d6436c82e173b32252c5e9c59757da
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396043"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Implantar um Servidor de Mediação no Construtor de Topologias Skype for Business Server
 
**Resumo:** Saiba como definir e implantar um Servidor de Mediação no Construtor de Topologias Skype for Business Server.
  
A Enterprise Voice de trabalho, conferência discda e aplicativos avançados Enterprise Voice (aplicativo do Grupo de Resposta, aplicativo estacionamento de chamada, cac (controle de admissão de chamada) e assim por diante) estão disponíveis nos pools de Front-End. A funcionalidade do Servidor de Mediação é criada no Servidor Front-End. Um Servidor de Mediação autônomo separado não é necessário. 
  
A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet. Para conectar sua infraestrutura Enterprise Voice ao provedor de tronco SIP, um Servidor de Mediação separado deve ser implantado.
  
A conexão entre Skype for Business Server (um Servidor de Mediação alocado em um pool de Front-End ou um Servidor de Mediação autônomo) e um gateway é definido como uma associação lógica chamada tronco. Os tópicos nesta seção descrevem como definir um tronco e como implantar um Servidor de Mediação autônomo, se você se conectar a um tronco SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definir um Servidor de Mediação no Construtor de Topologia

Você pode adicionar o Servidor de Mediação como uma função alocada em um pool de Front-End ou definir um pool de Servidor de Mediação autônomo separado.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para adicionar um Servidor de Mediação a um pool de Front-End

1. Iniciar Construtor de Topologias: clique em **Iniciar, em** Todos os **Programas, Skype for Business Server** **2015** e clique em Skype for Business Server **Construtor de 2015Topology**.
    
2. No Construtor de Topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um pool de Front-End.
    
3. Na árvore do console, clique com o botão direito do mouse no tipo de pool de Front-End que você deseja e clique em **Novo pool de Front-End..**.
    
4. Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.
    
5. Em **Selecionar funções de servidor alocadas**, verifique a opção **Collocate Mediation Server**.
    
    > [!NOTE]
    > Se o tipo de pool de Front-End selecionado for o Edição Enterprise, o componente do Servidor de Mediação será instalado em todos os Servidores Front-End desse pool de Front-End. 
  
    > [!NOTE]
    > O **pool de próximo salto** usado pelo Servidor de Mediação será o pool de Front-End no qual o Servidor de Mediação é alocado.
  
    > [!NOTE]
    > O **pool de Borda** usado pelo Servidor de Mediação será o mesmo pool de Borda associado ao pool de Front-End no qual o Servidor de Mediação é alocado.
  
6. Clique **em Tornar Padrão** para usar esse pool de Front-End para rotear chamadas para a PSTN.
    
7. Clique **em Concluir** quando terminar de associar um ou mais pares ao pool de Front-End.
    
    > [!NOTE]
    > Antes de prosseguir para a próxima etapa do processo de implantação do Enterprise Voice, certifique-se de que o pool do Servidor de Mediação (ou seja, pool de Front-End com o componente do Servidor de Mediação alocado) está usando os FQDNs especificados. 
  
8. Clique com o botão direito do **Skype for Business Server nó 2015** e clique em **Publicar Topologia**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Para adicionar um Servidor de Mediação autônomo

1. Iniciar Construtor de Topologias: clique em **Iniciar, em** Todos os **Programas, Skype for Business Server** **2015** e clique em Skype for Business Server **Construtor de 2015Topology**.
    
2. No Construtor de Topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um Servidor de Mediação.
    
3. Na árvore do console, clique com o botão direito do mouse no nó **Pools de** Mediação e clique em Pool **do Servidor de Mediação**.
    
4. Em **Definir Novo Pool de Mediação**, digite o FQDN (nome de domínio totalmente qualificado) do pool do Servidor de Mediação.
    
5. Em seguida, siga um destes procedimentos:
    
   - Se você quiser implantar vários Servidores de Mediação no pool para fornecer alta disponibilidade, selecione **Pool de vários computadores**.
    
     > [!NOTE]
     > Você deve [implantar para](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) dar suporte a pools de Servidor de Mediação que tenham vários Servidores de Mediação.
  
   - Se você quiser implantar apenas um Servidor de Mediação no pool porque não exige alta disponibilidade, selecione **Pool de computador único**. Ignore a etapa seguinte.
    
6. Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**. Repita esta etapa para todos os outros Servidores de Mediação que você deseja adicionar ao pool. Quando tiver definido todos os computadores no pool, clique em **Avançar**.
    
7. Na página **Selecionar o próximo** salto, clique em Pool de próximo **salto**, clique no FQDN do pool de Front-End que usará esse pool do Servidor de Mediação e clique em **Próximo**.
    
8. Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:
    
   - Se você quiser fornecer conectividade PSTN para usuários externos habilitados para Enterprise Voice, em **Selecionar Pool** de Borda usado por este Servidor de Mediação, clique no FQDN do pool do Servidor de Borda que usará esse pool de Servidor de Mediação para fornecer conectividade PSTN para esses usuários externos e clique em **Próximo**.
    
   - Se você não planeja habilitar usuários externos para Enterprise Voice ou se não quiser fornecer conectividade PSTN aos usuários quando eles estão fora da rede interna, clique em **Próximo**.
    
9. Clique com o botão direito do **Skype for Business Server nó 2015** e clique em **Publicar Topologia**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definir as portas de escuta do servidor de mediação

Siga as etapas deste tópico para usar o Construtor de Topologias para definir as portas de escuta que um Servidor de Mediação ou pool aceitará conexões de entrada de um ponto de gateway.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar as portas de escuta do servidor de mediação

1. Iniciar Construtor de Topologias: clique em **Iniciar, em** Todos os **Programas, Skype for Business Server** **2015** e clique em Skype for Business Server **Construtor de 2015Topology**.
    
2. No Construtor de Topologias, na árvore de console, expanda o nó **Pools de** Mediação e clique com o botão direito do mouse no Servidor de Mediação criado anteriormente.
    
3. Por padrão, as portas de escuta SIP no Servidor de Mediação são 5070 para tráfego TLS de Skype for Business Server e 5067 para tráfego TLS de pares (como gateways, PBXes ou SBCs). A porta TCP é desabilitada por padrão. Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.
    
4. Especifique o intervalo de portas de escuta TLS ou TCP desejado que o Servidor de Mediação aceitará conexões de entrada de gateways PSTN.
    
    > [!NOTE]
    > Não é necessário inserir um intervalo de portas TCP se a opção **Habilitar porta TCP** não estiver marcada. Essa configuração é opcional.
  

