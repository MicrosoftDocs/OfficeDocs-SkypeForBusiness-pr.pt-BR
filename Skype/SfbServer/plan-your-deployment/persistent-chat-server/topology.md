---
title: Plenejamento da topologia do Servidor de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Resumo: Leia este tópico para saber mais sobre componentes e topologias persistentes do servidor de chat no Skype for Business Server 2015.'
ms.openlocfilehash: c31cb8b0ada280b52d902e975f1bacf947fd19e7
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418270"
---
# <a name="plan-persistent-chat-server-topology"></a>Plenejamento da topologia do Servidor de Chat Persistente
 
**Resumo:** Leia este tópico para saber mais sobre os componentes e topologias persistentes do servidor de chat no Skype for Business Server 2015.
  
O servidor de chat persistente tem suporte para configurações de servidor único e de vários servidores. Você pode instalar o servidor de chat persistente em um servidor do Skype for Business Server 2015 Enterprise Edition ou Standard Edition. 

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Componentes persistentes do servidor de chat

O Servidor de Chat Persistente consiste nos seguintes componentes:
  
- Um ou mais computadores que executam o servidor de chat persistente e fornecimento dos seguintes serviços:
    
  - Serviço de chat persistente
    
  - Serviço de conformidade, que é ativado quando a conformidade é habilitada
    
- Um ou mais servidores (mais de um se o espelhamento for usado) executando o banco de dados back-end do SQL Server para hospedar o banco de dados de conteúdo de chat persistente no qual o conteúdo da sala de chat, salas e categorias são armazenados.
    
    > [!NOTE]
    > O banco de dados back-end armazena dados do histórico do chat, incluindo informações sobre categorias e salas de chat persistentes que são criadas. 
  
- Se a conformidade estiver habilitada, um ou mais servidores (mais de um se o espelhamento for usado) que executam o banco de dados back-end do SQL Server para hospedar o banco de dados de conformidade de chat persistente, onde os eventos de conformidade e o conteúdo de chat com a finalidade de conformidade são armazenados.
    
Para obter detalhes sobre os requisitos de hardware e software para o servidor de chat persistente, consulte [requisitos do servidor para o Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [requisitos de hardware e software para servidor de chat persistente no Skype for Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologias persistentes do servidor de chat

Você pode implantar um servidor de chat persistente em pools de servidor único ou de vários servidores e com topologia de pool único ou de vários pools. O servidor de chat persistente tem suporte para as seguintes topologias:
  
-  Servidor Standard Edition com Servidor de Chat Persistente colocado em um Servidor Front-End
    
-  Servidor Standard Edition com servidor de chat persistente em um servidor separado
    
-  Enterprise Edition Server com um único servidor de chat persistente em um servidor separado
    
-  Enterprise Edition Server com mais de um servidor de chat persistente em servidores separados
    
Embora você possa implantar o servidor de chat persistente em um servidor Standard Edition, lembre-se de que o desempenho e a escala serão afetados, e a alta disponibilidade não será uma opção. Portanto, é recomendável que você implante o chat persistente em um servidor Standard Edition principalmente para a prova de conceito e fins de avaliação. 
  
O Skype for Business Server 2015 oferece suporte a uma variedade de cenários de colocação, oferecendo a flexibilidade para reduzir os custos de hardware executando vários componentes em um servidor (se você tiver uma pequena organização) ou para executar componentes individuais em servidores diferentes ( Se você tiver uma organização maior que precisa de escalabilidade e desempenho). Você deve considerar os fatores de escalabilidade antes de se decidir se colocará os componentes. Os cenários de colocação são diferentes para servidores do Skype for Business Server 2015 Enterprise Edition e do Standard Edition. 
  
As próximas seções descrevem as topologias mais detalhadamente, incluindo cenários de colocação e opções para servidores de banco de dados back-end. Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [noções básicas de topologia para o Skype for Business server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Servidor Standard Edition com Servidor de Chat Persistente colocado em um Servidor Front-End

Com o Standard Edition, é possível colocar o Chat Persistente no Servidor Front-End. Essa é a configuração mais básica e simples. Você deve certificar-se de que o servidor front-end existente tem capacidade suficiente em termos de recursos físicos: CPU, memória, espaço em disco e assim por diante.
  
Além disso, você pode colocar o servidor back-end persistente do servidor de chat persistente e o banco de dados de conformidade de chat persistente (se habilitado) no servidor de back-end do SQL Server Express local. Você também pode optar por usar um SQL Server separado com uma instância dedicada. 
  
> [!IMPORTANT]
> Você não poderá adicionar mais servidores a um pool de servidores de chat persistente se o primeiro servidor de chat persistente estiver posicionado com um servidor front-end Standard Edition. É recomendável que você instale o primeiro servidor como uma instância autônoma para que você possa adicionar mais servidores mais tarde, se necessário. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Servidor Standard Edition com Servidor de Chat Persistente instalado em um servidor separado

Com o Standard Edition, você pode instalar o Servidor de Chat Persistente como uma instância autônoma e adicionar mais servidores posteriormente, se necessário.   
  
Você pode colocar o servidor back-end persistente do servidor de chat persistente e o banco de dados de conformidade de chat persistente (se habilitado) no servidor de back-end do SQL Server Express local. Você também pode optar por usar um SQL Server separado com uma instância dedicada. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Servidor Enterprise Edition com um único Servidor de Chat Persistente

Com o Enterprise Edition, você deve instalar o Servidor de Chat Persistente em um computador separado. Ou seja, não é possível colocar o Servidor de Chat Persistente no Servidor Front-End Enterprise Edition. Esta implantação requer um servidor separado que executa o servidor de chat persistente e o serviço de conformidade (se habilitado).
  
No entanto, você pode posicionar o banco de dados do SQL Server para servidor de chat persistente no banco de dados back-end de um pool de front-end da edição Enterprise.
  
> [!NOTE]
> Se você pretende usar Grupos de Disponibilidade AlwaysOn do SQL para HA DR, observe que eles não dão suporte a bancos de dados de Servidor de Chat Persistente. 
  
Se você colocar o banco de dados de chat persistente com o banco de dados back-end, poderá usar uma única instância do SQL Server para qualquer um ou todos os bancos de dados ou poderá usar uma instância separada do SQL Server para cada banco de dados.
  
> [!IMPORTANT]
> O servidor que hospeda o banco de dados de chat persistente pode hospedar outros bancos de dados. No entanto, quando você considera posicionar o banco de dados de chat persistente com outros bancos de dados, lembre-se de que, se você estiver armazenando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados de chat persistente pode crescer muito grande. Por esse motivo, não recomendamos posicionar o banco de dados de chat persistente com o banco de dados back-end. 
  
A figura a seguir mostra todos os componentes de uma topologia para um único servidor de chat persistente com conformidade habilitada (opcional).
  
**Topologia de servidor único**

![Servidor de chat persistente-topologia de servidor único](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Servidor Enterprise Edition com um múltiplos Servidores de Chat Persistente

Com a Enterprise Edition, você pode implantar uma topologia de vários servidores para aumentar a capacidade e a confiabilidade. Uma topologia de vários servidores é a mesma que a topologia de servidor único, exceto que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados para maior. A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastres permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em standby). Cada servidor pode oferecer suporte a quantos usuários simultâneos do 20.000, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores. Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio dos serviços de domínio Active Directory como o Skype for Business Server e o serviço de conformidade.
  
A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.
  
**Topologia de vários servidores**

![Servidor de chat persistente – topologia de vários servidores](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
As topologias de vários servidores fornecem a funcionalidade de pool de servidores. Em um pool de servidores, os serviços de chat persistente se comunicam e compartilham dados. Por exemplo, o histórico de chats originalmente lançado em um serviço de chat persistente está disponível em qualquer serviço de chat persistente do sistema. Um arquivo carregado por meio de um serviço de chat persistente pode ser acessado por qualquer serviço de chat persistente. Os usuários podem ser conectados a diferentes servidores de front-end do servidor de chat persistente e podem se comunicar uns com os outros. A porta padrão do TCP 8011 conecta um servidor a um pool de servidores e é usada pelos serviços de chat persistente para se comunicar entre si ou para fins administrativos.
  
Por exemplo, em uma implantação de servidor de chat persistente de quatro servidores, em que os usuários do 80.000 podem ser conectados simultaneamente a chats persistentes, a carga é distribuída uniformemente em 20.000 usuários por servidor. Se um servidor ficar indisponível, os usuários que estiverem conectados a esse servidor perderão o acesso ao servidor de chat persistente. Os usuários desconectados serão automaticamente transferidos para os servidores remanescentes até que o servidor indisponível seja restaurado. 
  

