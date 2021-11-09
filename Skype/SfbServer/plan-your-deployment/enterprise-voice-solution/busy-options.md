---
title: Planejar opções de ocupado para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Leia sobre o recurso Opções de Ocupado Skype for Business Server.
ms.openlocfilehash: b233260327688830a338989c14ef0eb24ade781e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854225"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planejar opções de ocupado para Skype for Business Server
 
Leia sobre o recurso Opções de Ocupado Skype for Business Server.
  
Opções de Ocupado é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. Chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal. 
  
A política Opções de Ocupado é suportada para failover e recuperação de desastres em Pools front-end emparelhados e Servidores de Filial (SBS).
  
Este tópico descreve os recursos das Opções de Ocupado. Para obter informações sobre como instalar e configurar Opções de Ocupado, consulte [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Opções de configuração

Se Opções de Ocupado estiver habilitada para a organização, todos os usuários da sua organização, usuários Enterprise Voice usuários que não Enterprise Voice usuários, poderão usar os seguintes recursos:
  
- Ocupado em Ocupado - Em que novas chamadas de entrada serão rejeitadas com um sinal de ocupado se o usuário estiver ocupado.
    
- Caixa postal em Ocupado - Em que novas chamadas de entrada serão encaminhadas para a caixa postal se o usuário estiver ocupado.
    
O recurso Opções de Ocupado fornece o recurso de failover. Se ocorrer um problema e os usuários falharem em outro Servidor Front-End ou em outro pool no Skype for Business Server, suas configurações de Opções de Ocupado serão preservadas.
  
Independentemente de como suas opções de ocupado estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências. 
  
Após a configuração, a configuração Opções de Ocupado está em vigor para todos os Skype for Business de chamada e clientes do usuário. Com base nas configurações de Opções de Ocupado do usuário, a chamada rejeitada ou enviada para a caixa postal não tocaria em nenhum dos dispositivos de chamada do usuário, incluindo Macintosh, Windows Desktop, clientes móveis ou telefones IP nos quais o usuário está conectado. 
  
Os usuários verão notificações de chamada perdida em seus Skype for Business e dispositivos, e eles também serão notificados por email. Os chamadores cuja chamada foi rejeitada devido ao Ocupado ocupado verão uma notificação em seu cliente Skype for Business informando que o usuário que tentou alcançar está ocupado em outra chamada.
  
Você pode configurar o recurso Opções de Ocupado usando Skype for Business cmdlets do PowerShell para:
  
- Habilitar ou desabilitar a política de Voz de Opções de Ocupado para o Enterprise.
    
- Administro Ocupado no Ocupado ou Caixa Postal no Ocupado para todos os usuários no Enterprise.
    
- Administro Ocupado no Ocupado ou Caixa Postal no Ocupado para todos os usuários que estão em um pool de Front-End específico.
    
- Administro Ocupado no Ocupado ou Caixa Postal em Ocupado para uma lista de usuários.
    
- Administro Ocupado no Ocupado ou Caixa Postal em Ocupado para um único usuário.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilidade com aplicativos Voice

Opções de Ocupado fornece interoperabilidade com os seguintes aplicativos de Voz no Skype for Business:
  
- Grupos de resposta (RGS)
    
  - Opções de ocupado definidas em números do Grupo de Resposta serão ignoradas pelo sistema; várias chamadas simultâneas serão permitidas. 
    
  - A experiência de roteamento atual do Attendant em Grupos de Resposta permanecerá inalterada para as configurações Agentes com Opções de Ocupado.
    
  - As chamadas provenientes dos Grupos de Resposta para os usuários que são Agentes de Grupos de Resposta não serão controladas pelas configurações de Opções de Ocupado e a experiência atual do RGS será mantida.
    
  - As chamadas não relacionadas ao RGS aos Agentes serão acodadas pelas configurações de Opções de Ocupado.
    
- Chamada de Equipe
    
  - As chamadas de entrada para usuários que estão configuradas para uma Chamada de Equipe serão priorizadas para ignorar as configurações Ocupado no Ocupado e na Caixa Postal no Ocupado.
    
  - A experiência atual de Chamada de Equipe permanecerá inalterada com Opções de Ocupado definidas para os usuários.
    
  - As chamadas relacionadas a chamadas não relacionadas a esses usuários serão acodadas pelas configurações de Opções de Ocupado.
    
- Delegação de chefe/administrador 
    
  - As chamadas de entrada para usuários que estão configuradas para uma Delegação de Chefe/Administrador como Chefe ou Administrador serão priorizadas para ignorar as configurações Ocupado no Ocupado e Caixa Postal no Ocupado.
    
  - A experiência atual de Delegação de Chefe/Administrador permanecerá inalterada com Opções de Ocupado definidas para administradores ou chefe.
    
  - As chamadas relacionadas à Delegação não Chefe/Administrador para Administradores serão agravadas com suas configurações de Opções de Ocupado.
    
- Aparência de linha compartilhada 
    
  - As configurações de Opções de Ocupado em contas de usuário configuradas para Aparência de Linha Compartilhada serão ignoradas. 
    
  - Em vez disso, as opções de Ocupado ocupado e caixa postal em Ocupado da Aparência de Linha Compartilhada serão adidadas.
    
- Serviço de Estacionamento de Chamada 
    
  - As chamadas estacionadas que não foram recuperadas e estão chamando de volta devido ao tempo de saída terão permissão para tocar para o usuário que estacionou a chamada pelas Opções de Ocupado. 
    
- Conferência de Chamada
    
  - Os usuários em chamadas de conferência são considerados Ocupados e novas chamadas de entrada serão rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal de acordo com suas configurações de Opções de Ocupado.
    
  - Os usuários em conferências não são impedidos de iniciar novas chamadas ou conferências por Opções de Ocupado.
    
  - Os usuários em conferências ainda podem receber novos convites de conferência, mas novas chamadas ponto a ponto serão rejeitadas de acordo com suas configurações de Opções de Ocupado.
    
- Toque Simultâneo e Encaminhamento de Chamada
    
    O recurso Ocupado no Ocupado não foi projetado para funcionar com o Anel Simultâneo e o Encaminhamento de Chamada.
    

