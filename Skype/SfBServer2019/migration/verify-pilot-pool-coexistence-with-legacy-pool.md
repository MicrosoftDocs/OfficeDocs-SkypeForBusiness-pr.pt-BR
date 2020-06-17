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
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751653"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificar coexistência de pool piloto com pool herdado

 **Neste artigo**
  
[Verificar se os serviços do Skype for Business Server 2019 foram iniciados](#sectionSection0)
  
[Abrir o painel de controle do Skype for Business Server 2019](#sectionSection1)
  
[Não tente abrir a topologia no construtor de topologias herdadas](#sectionSection2)
  
Depois de implantar o pool piloto, você deve verificar a coexistência de dois pools usando ferramentas administrativas para exibir as informações dos pools. Para os pools do Skype for Business Server 2019 e pools herdados, você deve usar o painel de controle do Skype for Business Server 2019 e as ferramentas do construtor de topologia. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Verificar se os serviços do Skype for Business Server 2019 foram iniciados
<a name="sectionSection0"> </a>

1. No servidor front-end do Skype for Business Server 2019, navegue até o mini-aplicativo applet administrativo.
    
2. Verifique se os serviços a seguir estão sendo executados no servidor Front End:

    - Agente de serviço de registro em log centralizado
    - Compartilhamento de aplicativo
    - Serviço de teste de áudio
    - Audioconferências/Videoconferências
    - Estacionamento de chamada
    - Comunicado de conferência
    - Atendedor de conferência
    - Front-end
    - Conferência de IM
    - Mediação
    - Agente replicador de réplica
    - Grupo de Resposta
    - Webconferência
    - Gateway de conversão XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abrir o painel de controle do Skype for Business Server 2019
<a name="sectionSection1"> </a>

A partir do servidor front-end na sua implantação do Skype for Business Server 2019, abra o painel de controle do Skype for Business Server 2019 e selecione o pool herdado. Repita o procedimento para abrir o pool do Skype for Business Server 2019.
  
> [!IMPORTANT]
> No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel de controle do Skype for Business Server. 
  
Essa topologia agora inclui funções de servidor herdadas e do Skype for Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Não tente abrir a topologia no construtor de topologias herdadas
<a name="sectionSection2"> </a>

A topologia só pode ser exibida usando o construtor de topologias do Skype for Business Server 2019. O construtor de topologias do Skype for Business Server 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e a instalação herdada.

  

