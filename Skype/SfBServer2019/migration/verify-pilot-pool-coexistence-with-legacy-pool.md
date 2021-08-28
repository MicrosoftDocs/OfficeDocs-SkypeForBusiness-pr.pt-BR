---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: 5d2e6adad0f3297260137df0abcd082b750f0345
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606810"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificar coexistência de pool piloto com pool herdado

 **Neste artigo**
  
[Verifique se os Skype for Business Server 2019 foram iniciados](#sectionSection0)
  
[Abra o painel Skype for Business Server 2019](#sectionSection1)
  
[Não tente abrir a topologia no Construtor de Topologias herdada](#sectionSection2)
  
Depois de implantar o pool piloto, você deve verificar a coexistência de dois pools usando ferramentas administrativas para exibir as informações dos pools. Para os pools Skype for Business Server 2019 e pools herdado, você deve usar as ferramentas painel de controle Skype for Business Server 2019 e construtor de topologias. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Verifique se os Skype for Business Server 2019 foram iniciados
<a name="sectionSection0"> </a>

1. No servidor front-end Skype for Business Server 2019, navegue até o applet Ferramentas Administrativas\Serviços.
    
2. Verifique se os serviços a seguir estão sendo executados no servidor Front End:

    - Agente de Serviço de Log Centralizado
    - Compartilhamento de aplicativo
    - Serviço de Teste de Áudio
    - Audioconferências/Videoconferências
    - Estacionamento de Chamada
    - Comunicado de Conferência
    - Atendedor de Conferência
    - Front-end
    - Conferência de IM
    - Mediação
    - Replica Replicator Agent
    - Grupo de Resposta
    - Conferência pela Web
    - Gateway de tradução XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abra o painel Skype for Business Server 2019
<a name="sectionSection1"> </a>

No Servidor front-end em sua implantação Skype for Business Server 2019, abra o Painel de Controle Skype for Business Server 2019 e selecione o pool herdado. Repita o procedimento para abrir o pool Skype for Business Server 2019.
  
> [!IMPORTANT]
> No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel Skype for Business Server Controle. 
  
Essa topologia agora inclui funções de servidor herdados e Skype for Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Não tente abrir a topologia no Construtor de Topologias herdada
<a name="sectionSection2"> </a>

A topologia só pode ser visualizada usando Skype for Business Server Construtor de Topologias 2019. O Skype for Business Server Construtor de Topologias 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e a instalação herdado.

  

