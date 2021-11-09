---
title: Planejar a topologia do Servidor de Chat Persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Resumo: leia este tópico para saber mais sobre componentes e topologias do Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 1b57d9d9ace6e51001acfa39101eb185a8e00939
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862068"
---
# <a name="plan-persistent-chat-server-topology"></a>Planejar a topologia do Servidor de Chat Persistente
 
**Resumo:** Leia este tópico para saber mais sobre componentes e topologias do Servidor de Chat Persistente no Skype for Business Server 2015.
  
O Servidor de Chat Persistente dá suporte a configurações de servidor único e de vários servidores. Você pode instalar o Servidor de Chat Persistente em um Skype for Business Server 2015 Edição Enterprise ou Edição Standard Server. 

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Componentes do Servidor de Chat Persistente

O Servidor de Chat Persistente consiste nos seguintes componentes:
  
- Um ou mais computadores executando o Servidor de Chat Persistente e fornecendo os seguintes serviços:
    
  - Serviço de Chat Persistente
    
  - Serviço de conformidade, que é ativado quando a conformidade é habilitada
    
- Um ou mais servidores (mais de um se o espelhamento for usado) executando o banco de dados back-end SQL Server para hospedar o banco de dados de conteúdo de Chat Persistente em que o conteúdo, salas e categorias da sala de chat são armazenados.
    
    > [!NOTE]
    > O banco de dados back-end armazena dados de histórico de chat, incluindo informações sobre categorias e salas de Chat Persistente criadas. 
  
- Se a conformidade estiver habilitada, um ou mais servidores (mais de um se o espelhamento for usado) executando o banco de dados back-end do SQL Server para hospedar o banco de dados de Conformidade de Chat Persistente, onde eventos de conformidade e conteúdo de chat para fins de conformidade são armazenados.
    
Para obter detalhes sobre requisitos de hardware e software para o Servidor de Chat Persistente, consulte Requisitos de servidor para [o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e requisitos de hardware e software para o Servidor de Chat Persistente [no Skype for Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologias do Servidor de Chat Persistente

Você pode implantar o Servidor de Chat Persistente em pools de servidor único ou de vários servidores e com topologia de pool único ou de vários pools. O Servidor de Chat Persistente dá suporte às seguintes topologias:
  
-  Edição Standard Servidor com Servidor de Chat Persistente alocado no Servidor Front-End
    
-  Edição Standard Servidor com Servidor de Chat Persistente em um servidor separado
    
-  Edição Enterprise Servidor com um único Servidor de Chat Persistente em um servidor separado
    
-  Edição Enterprise Servidor com mais de um Servidor de Chat Persistente em servidores separados
    
Embora você possa implantar o Servidor de Chat Persistente em um servidor Edição Standard, esteja ciente de que o desempenho e a escala serão afetados e a alta disponibilidade não é uma opção. Portanto, é recomendável implantar o Chat Persistente em um servidor Edição Standard principalmente para fins de prova de conceito e avaliação. 
  
Skype for Business Server 2015 oferece suporte a uma variedade de cenários de localização, fornecendo a flexibilidade para economizar custos de hardware executando vários componentes em um servidor (se você tiver uma pequena organização) ou para executar componentes individuais em servidores diferentes (se você tiver uma organização maior que precise de escalabilidade e desempenho). Você deve considerar fatores de escalabilidade antes de decidir se deve recalocar componentes. Os cenários de localização diferem para os servidores Skype for Business Server 2015 Edição Enterprise e Edição Standard 2015. 
  
As seções a seguir descrevem as topologias com mais detalhes, incluindo cenários de colocação e opções para os servidores de banco de dados back-end. Para obter detalhes sobre a localização de todas as funções de servidor e bancos de dados, consulte [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Edição Standard Servidor com Servidor de Chat Persistente alocado no Servidor Front-End

Com Edição Standard, você pode colocar Chat Persistente no Servidor front-end. Essa é a configuração mais simples e básica. Você deve garantir que o Servidor Front-End existente tenha capacidade suficiente em termos de recursos físicos: CPU, memória, espaço em disco e assim por diante.
  
Além disso, você pode coloar o servidor back-end do Servidor de Chat Persistente e o banco de dados de Conformidade de Chat Persistente (se habilitado) no servidor SQL Server Express back-end local. Você também pode optar por usar um SQL Server separado com uma instância dedicada. 
  
> [!IMPORTANT]
> Não é possível adicionar servidores adicionais a um pool de Servidor de Chat Persistente se o primeiro Servidor de Chat Persistente for alocado com um servidor Edição Standard Front-End. É recomendável instalar o primeiro servidor como uma instância autônoma para que você possa adicionar mais servidores posteriormente, se necessário. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Edição Standard Servidor com Servidor de Chat Persistente instalado em um servidor separado

Com Edição Standard, você pode instalar o Servidor de Chat Persistente como uma instância autônoma e adicionar mais servidores mais tarde, se necessário. 
  
Você pode coloar o servidor back-end do Servidor de Chat Persistente e o banco de dados de Conformidade de Chat Persistente (se habilitado) no servidor back-end SQL Server Express local. Você também pode optar por usar um SQL Server separado com uma instância dedicada. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Edição Enterprise Servidor com um único Servidor de Chat Persistente

Com Edição Enterprise, você deve instalar o Servidor de Chat Persistente em um computador separado. Ou seja, você não pode reajustar o Servidor de Chat Persistente no servidor Edição Enterprise Front-End. Essa implantação requer um servidor separado que executa o Servidor de Chat Persistente e o serviço de Conformidade (se habilitado).
  
No entanto, você pode SQL Server o banco de dados de SQL Server de Chat Persistente no banco de dados back-end de um pool Edição Enterprise front-end.
  
> [!NOTE]
> Se você planeja usar SQL Grupos de Disponibilidade AlwaysOn para HA DR, observe que ele não é suportado para bancos de dados do Servidor de Chat Persistente. 
  
Se você conocar o banco de dados de Chat Persistente com o banco de dados back-end, poderá usar uma única instância do SQL Server para qualquer ou todos os bancos de dados ou pode usar uma instância separada de SQL Server para cada banco de dados.
  
> [!IMPORTANT]
> O servidor que hospeda o banco de dados de Chat Persistente pode hospedar outros bancos de dados. No entanto, quando você considerar a collocação do banco de dados de Chat Persistente com outros bancos de dados, esteja ciente de que, se você estiver armazenar as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados de Chat Persistente poderá crescer muito grande. Por esse motivo, não recomendamos a localização do banco de dados de Chat Persistente com o banco de dados back-end. 
  
A figura a seguir mostra todos os componentes de uma topologia para um único Servidor de Chat Persistente com conformidade habilitada (opcional).
  
**Topologia de Servidor Único**

![Servidor de Chat Persistente - Topologia de Servidor Único.](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Edição Enterprise Servidor com vários Servidores de Chat Persistente

Com Edição Enterprise, você pode implantar uma topologia de vários servidores para maior capacidade e confiabilidade. Uma topologia de vários servidores é a mesma que a topologia de servidor único, exceto que vários servidores hospedam o Servidor de Chat Persistente e podem ser dimensionados mais alto. A topologia de vários servidores pode incluir até quatro computadores ativos executando o Servidor de Chat Persistente (configurações de alta disponibilidade e recuperação de desastres permitirão até oito, mas apenas quatro podem estar ativos e os quatro restantes em espera). Cada servidor pode suportar até 20.000 usuários simultâneos, para um total de 80.000 usuários simultâneos conectados a um pool de Servidores de Chat Persistente com 4 servidores. Vários computadores que executam o Servidor de Chat Persistente devem residir no mesmo domínio dos Serviços de Domínio do Active Directory Skype for Business Server e no serviço de Conformidade.
  
A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores executando o Servidor de Chat Persistente, o serviço de Conformidade opcional e um banco de dados de conformidade separado.
  
**Topologia de Vários Servidores**

![Servidor de Chat Persistente - Topologia de Vários Servidores.](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
As topologias de vários servidores fornecem a funcionalidade de pool de servidores. Em um pool de servidores, os serviços de Chat Persistente se comunicam e compartilham dados. Por exemplo, o histórico de chat que foi originalmente postado em um serviço de Chat Persistente está disponível em qualquer serviço de Chat Persistente no sistema. Um arquivo carregado por meio de um serviço de Chat Persistente pode ser acessado por qualquer serviço de Chat Persistente. Os usuários podem ser conectados a diferentes Servidores Front-End do Servidor de Chat Persistente e podem se comunicar uns com os outros. A porta padrão do TCP 8011 conecta um servidor a um pool de servidores e é usada pelos serviços de Chat Persistente para se comunicar entre si ou para fins administrativos.
  
Por exemplo, em uma implantação do Servidor de Chat Persistente de quatro servidores, onde 80.000 usuários podem estar simultaneamente no Chat Persistente, a carga é distribuída uniformemente em 20.000 usuários por servidor. Se um servidor ficar indisponível, os usuários conectados a esse servidor perderão o acesso ao Servidor de Chat Persistente. Os usuários desconectados serão automaticamente transferidos para os servidores restantes até que o servidor disponível seja restaurado. 
  

