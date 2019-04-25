---
title: Verificar coexistência de pool piloto com pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processo para verificar a coexistência do pool piloto com o pool herdado.
ms.openlocfilehash: ed3809bdde3109bdbd341c42eed0dc1d8cecd11f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231340"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Verificar coexistência de pool piloto com pool herdado

 **Neste artigo**
  
[Verifique se que Skype para Business Server 2019 serviços foram iniciados](#sectionSection0)
  
[Abra o Skype para painel de controle do Business Server 2019](#sectionSection1)
  
[Não tente abrir a topologia no construtor de topologia herdada](#sectionSection2)
  
Depois de implantar o pool piloto, você precisará verificar a coexistência dos dois pools usando as ferramentas administrativas para exibir as informações do pool. Para Skype para pools herdados e pools de negócios 2019 de servidor, você deve usar o Skype para as ferramentas do painel de controle do Business Server 2019 e o construtor de topologia. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Verifique se que Skype para Business Server 2019 serviços foram iniciados
<a name="sectionSection0"> </a>

1. No Skype para Business Server 2019 servidor Front-End, navegue até o applet ferramentas administrativas \ Serviços.
    
2. Verifique se os seguintes serviços estão funcionando no servidor Front-End:

    - Agente de Serviço de Log Centralizado
    - Compartilhamento de Aplicativos
    - Serviço de teste de áudio
    - Conferência de áudio/vídeo
    - Estacionamento de Chamada
    - Comunicado de conferência
    - Atendedor de conferência
    - Front-end
    - Conferência de IM
    - Mediação
    - Agente replicador de réplica
    - Grupo de Resposta
    - Webconferência
    - Conversão de Gateway XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Abra o Skype para painel de controle do Business Server 2019
<a name="sectionSection1"> </a>

Do servidor Front-End no seu Skype para implantação Business Server 2019, abra o Skype para painel de controle do Business Server 2019 e selecione o pool herdado. Repita o procedimento para abrir o Skype para Business Server 2019 pool.
  
> [!IMPORTANT]
> Em Skype para Business Server 2019, você deve atualizar Silverlight para Silverlight versão 5 antes de usar o Skype para painel de controle do servidor de negócios. 
  
Essa topologia agora inclui herdado e Skype Business Server 2019 para funções de servidor. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Não tente abrir a topologia no construtor de topologia herdada
<a name="sectionSection2"> </a>

Se você tentar abrir a topologia usando o construtor de topologia herdada, você encontrará o erro abaixo. A topologia só pode ser exibida usando Skype para o construtor de topologias do Business Server 2019. O Skype para o construtor de topologias do Business Server 2019 deve ser usado para criar pools do Skype para Business Server 2019 e a instalar herdada.

  

