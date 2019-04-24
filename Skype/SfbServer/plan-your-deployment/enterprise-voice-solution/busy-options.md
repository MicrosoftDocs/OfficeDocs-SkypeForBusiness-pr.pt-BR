---
title: Planejar Opções de Disponibilidade no Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Leia sobre o recurso de opções ocupado no Skype for Business Server.
ms.openlocfilehash: 41e34dbb4eaf4a264ba1cec3756cc53c78992611
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207073"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planejar Opções de Disponibilidade no Skype for Business Server
 
Leia sobre o recurso de opções ocupado no Skype for Business Server.
  
O recurso Opções de Disponibilidade é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada serão tratadas quando o usuário já estiver em uma chamada ou em conferência ou tiver colocado uma chamada em espera. As chamadas novas ou de entrada poderão ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal. 
  
Essa política tem suporte para failover e recuperação de desastre em Pools de Front-Ends e em SBSs (Servidores de Ramificação Persistente) emparelhados.
  
Este tópico descreve as configurações de Opções de Disponibilidade. Para obter informações sobre como instalar e configurar o recurso Opções de Disponibilidade, veja [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Opções de configuração

Se o recurso Opções de Disponibilidade estiver habilitado para a organização, todos os usuários da empresa, tanto os usuários Enterprise Voice quanto os não Enterprise Voice, poderão usar os seguintes recursos:
  
- Sinal de Ocupado quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão rejeitadas com um sinal de ocupado.
    
- Caixa Postal quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão encaminhadas para a caixa postal.
    
O recurso Opções de Disponibilidade fornece a capacidade de failover. Se ocorrer um problema e usuários realizar failover para outro servidor Front-End ou para outro pool no Skype para Business Server, suas configurações de opções ocupado serão preservadas.
  
Qualquer que seja a maneira de configurar as opções de disponibilidade, os usuários em uma chamada ou em conferência (ou aqueles com uma chamada em espera) não serão impedidos de iniciar novas chamadas ou conferências.   
  
Após a configuração, a configuração de opções de disponibilidade está em vigor para Skype do todos os usuários para clientes e dispositivos de chamada de negócios. Com base nas configurações de Opções de Disponibilidade do usuário, a chamada que é rejeitada ou enviada para a caixa postal não tocará em nenhum dos dispositivos de chamada do usuário (incluindo Macintosh, Área de Trabalho do Windows, clientes móveis ou telefones IP) nos quais ele esteja conectado. 
  
Os usuários verão notificações de chamadas perdidas em seu Skype para dispositivos e clientes corporativos e eles serão notificados por email também. Os chamadores cuja chamada foi rejeitada devido à ocupado em ocupado verá uma notificação em seu Skype para o cliente de negócios, informando que o usuário que tentaram acessar está ocupado em outra chamada.
  
Você pode configurar o recurso de opções ocupado usando Skype para os cmdlets do PowerShell de negócios:
  
- Habilitar ou desabilitar a política de voz do recurso Opções de Disponibilidade para a empresa.
    
- Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para todos os usuários da empresa.
    
- Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para todos os usuários residentes em um Pool de Front-Ends específico.
    
- Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para uma lista de usuários.
    
- Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para um único usuário.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilidade com aplicativos de voz

Opções de ocupado fornece interoperabilidade com os seguintes aplicativos de voz no Skype para negócios:
  
- Grupos de Resposta (RGS)
    
  - As configurações de Opções de Disponibilidade definidas nos números de Grupo de Resposta serão ignoradas pelo sistema; várias chamadas simultâneas serão permitidas.  
    
  - A experiência de encaminhamento do Atendedor atual em Grupos de Resposta permanecerá inalterada para os Agentes com configurações de Opções de Disponibilidade.
    
  - As chamadas de Grupos de Resposta para usuários que são Agentes de Grupos de Resposta não serão controladas pelas configurações de Opções de Disponibilidade. Além disso, a experiência de RGS atual será mantida.
    
  - As chamadas para os Agentes, que não estiverem relacionadas a RGS, serão tratadas de acordo com as configurações de Opções de Disponibilidade.
    
- Chamada de Equipe
    
  - Chamadas de entrada para os usuários que estiverem configurados para uma chamada de equipe vai ser priorizadas para ignorar ocupado em ocupado e caixa postal nas configurações de ocupado.
    
  - A experiência de Chamada de Equipe atual permanecerá inalterada com as configurações de Opções de Disponibilidade definidas para os usuários.
    
  - As chamadas que não estiverem relacionadas à Chamada de Equipe serão tratadas conforme as configurações de Opções de Disponibilidade.
    
- Delegação de chefe/administrador  
    
  - Chamadas de entrada para os usuários que estiverem configurados para uma delegação de administração do chefe tanto como chefe ou um administrador vai ser priorizadas ignorar ocupado em ocupado e caixa postal nas configurações de ocupado.
    
  - A experiência de Delegação de Chefe/Administrador atual permanecerá inalterada com as configurações de Opções de Disponibilidade definidas para administradores ou chefe.
    
  - As chamadas para administradores, que não estiverem relacionadas à Delegação de Chefe/Administrador, serão tratadas conforme as configurações de Opções de Disponibilidade.
    
- Aparência de linha compartilhada    
    
  - As configurações de Opções de Disponibilidade nas contas de usuário configuradas para Aparência de Linha Compartilhada serão ignoradas.  
    
  - Ocupado nativo da aparência da linha compartilhada em ocupado e caixa postal em Opções de ocupado serão atendido em vez disso.
    
- Serviço de estacionamento de chamada  
    
  - As chamadas estacionadas que não foram atendidas e que retornam a tocar após determinado período poderão serão atendidas pelo usuário que as estacionou utilizando as configurações de Opções de Disponibilidade.  
    
- Chamada em conferência
    
  - Os usuários que estiverem em chamadas em conferência terão o status Ocupado, e as novas chamadas de entrada serão rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal conforme as configurações de Opções de Disponibilidade.
    
  - Os usuários em conferência não são impedidos de iniciar novas chamadas ou conferências conforme as configurações de Opções de Disponibilidade.
    
  - Os usuários em conferência ainda podem receber novos convites de conferência, mas novas chamadas ponto a ponto serão rejeitadas conforme as configurações de Opções de Disponibilidade.
    
- Toque Simultâneo e Encaminhamento de Chamadas
    
    O recurso Busy on Busy não é projetado para funcionar com Toque Simultâneo e Encaminhamento de Chamadas.
    

