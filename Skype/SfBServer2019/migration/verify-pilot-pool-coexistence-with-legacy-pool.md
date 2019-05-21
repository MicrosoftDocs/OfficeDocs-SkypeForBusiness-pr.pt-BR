---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: dd2edd2e6ecef26b22ba9bf5c093c631866110ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280650"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificar coexistência de pool piloto com pool herdado

 **Neste artigo**
  
[Verifique se os serviços do Skype for Business Server 2019 começaram](#sectionSection0)
  
[Abrir o painel de controle do Skype for Business Server 2019](#sectionSection1)
  
[Não tente abrir a topologia no construtor de topologias herdadas](#sectionSection2)
  
Depois de implantar o pool piloto, você precisa verificar a coexistência dos dois pools usando as ferramentas administrativas para exibir as informações de pool. Para os pools do Skype for Business Server 2019 e pools herdados, você deve usar o painel de controle do Skype for Business Server 2019 e ferramentas do construtor de topologia. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Verifique se os serviços do Skype for Business Server 2019 começaram
<a name="sectionSection0"> </a>

1. No servidor front-end do Skype for Business Server 2019, navegue até o applet administrador do Tools\Services.
    
2. Verifique se os seguintes serviços estão em execução no servidor front-end:

    - Agente de Serviço de Log Centralizado
    - Compartilhamento de Aplicativos
    - Serviço de teste de áudio
    - Conferência de áudio/vídeo
    - Estacionamento de Chamada
    - Comunicado de conferência
    - Atendedor de conferência
    - Front-end
    - Conferência de mensagem instantânea
    - Mediação
    - Agente duplicador de réplica
    - Grupo de Resposta
    - Webconferência
    - XMPP traduzir o gateway

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abrir o painel de controle do Skype for Business Server 2019
<a name="sectionSection1"> </a>

A partir do servidor front-end na implantação do Skype for Business Server 2019, abra o painel de controle do Skype for Business Server 2019 e selecione o pool herdado. Repita o procedimento para abrir o pool do Skype for Business Server 2019.
  
> [!IMPORTANT]
> No Skype for Business Server 2019, você deve atualizar o Silverlight para o Silverlight versão 5 antes de usar o painel de controle do Skype for Business Server. 
  
Essa topologia agora inclui funções de servidor herdadas e do Skype for Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Não tente abrir a topologia no construtor de topologias herdadas
<a name="sectionSection2"> </a>

Se você tentar abrir a topologia usando o construtor de topologias herdado, o erro será encontrado abaixo. A topologia só pode ser visualizada usando o construtor de topologias do Skype for Business Server 2019. O construtor de topologia do Skype for Business Server 2019 deve ser usado para criar pools para o Skype for Business Server 2019 e para a instalação herdada.

  

