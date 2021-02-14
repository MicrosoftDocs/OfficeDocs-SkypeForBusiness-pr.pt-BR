---
title: Planejar opções de ocupado para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Leia sobre o recurso Opções de Ocupado no Skype for Business Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813691"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planejar opções de ocupado para o Skype for Business Server
 
Leia sobre o recurso Opções de Ocupado no Skype for Business Server.
  
Opções de Ocupado é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. Chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal. 
  
A política de Opções de Ocupado é suportada para failover e recuperação de desastre em Pools de Front-End emparelhados e Servidores de Filial Survivable (SBS).
  
Este tópico descreve os recursos das Opções de Ocupado. Para obter informações sobre como instalar e configurar Opções de Ocupado, consulte Instalar e configurar Opções de Ocupado [para o Skype for Business Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)
  
## <a name="configuration-options"></a>Opções de configuração

Se as Opções de Ocupado estiver habilitada para a organização, todos os usuários da sua organização, tanto os usuários do Enterprise Voice quanto os que não são do Enterprise Voice, poderão usar os seguintes recursos:
  
- Ocupado quando ocupado - Em que novas chamadas de entrada serão rejeitadas com um sinal de ocupado se o usuário estiver ocupado.
    
- Caixa Postal quando Ocupado - Em que novas chamadas de entrada serão encaminhadas para a caixa postal se o usuário estiver ocupado.
    
O recurso Opções de Ocupado fornece o recurso de failover. Se ocorrer um problema e os usuários efetuarem fail over para outro Servidor front-end ou para outro pool no Skype for Business Server, suas configurações de Opções de Ocupado serão preservadas.
  
Independentemente de como suas opções de ocupado estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências. 
  
Após a configuração, a configuração Opções de Ocupado está em vigor para todos os clientes e dispositivos de chamada do Skype for Business do usuário. Com base nas configurações de Opções de Ocupado do usuário, a chamada que é rejeitada ou enviada para a caixa postal não tocaria em nenhum dos dispositivos de chamada do usuário, incluindo Macintosh, Área de Trabalho do Windows, clientes móveis ou telefones IP, nos quais o usuário está conectado. 
  
Os usuários verão notificações de chamada perdida em seus clientes e dispositivos do Skype for Business e também serão notificados por email. Os chamadores cuja chamada foi rejeitada devido a Ocupado quando Ocupado verão uma notificação em seu cliente do Skype for Business informando que o usuário que tentou acessar está ocupado em outra chamada.
  
Você pode configurar o recurso Opções de Ocupado usando os cmdlets do PowerShell do Skype for Business para:
  
- Habilitar ou desabilitar a política de Voz de Opções de Ocupado para a empresa.
    
- Administrar a caixa postal quando ocupado ou quando ocupado para todos os usuários na empresa.
    
- Administrar a caixa postal quando ocupado ou quando ocupado para todos os usuários que estão em um pool de Front-End específico.
    
- Administrar a caixa postal quando ocupado ou ocupado para uma lista de usuários.
    
- Administrar a caixa postal quando ocupado ou quando ocupado para um único usuário.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilidade com aplicativos de voz

Opções de ocupado fornece interoperabilidade com os seguintes aplicativos de voz no Skype for Business:
  
- Grupos de Resposta (RGS)
    
  - Opções de Ocupado definidas nos números do Grupo de Resposta serão ignoradas pelo sistema; várias chamadas simultâneas serão permitidas. 
    
  - A experiência de roteamento atual do Attendant nos Grupos de Resposta permanecerá inalterada para os Agentes com as configurações de Opções de Ocupado.
    
  - As chamadas provenientes dos Grupos de Resposta para os usuários que são Agentes de Grupos de Resposta não serão aceleradas pelas configurações de Opções de Ocupado e a experiência atual do RGS será mantida.
    
  - As chamadas não relacionadas a RGS para os Agentes serão aprinciadas pelas configurações de Opções de Ocupado.
    
- Chamada de Equipe
    
  - As chamadas de entrada para usuários que estão configuradas para uma Chamada de Equipe serão priorizadas para ignorar as configurações de Ocupado quando Ocupado e Caixa Postal quando Ocupado.
    
  - A experiência atual da Chamada de Equipe permanecerá inalterada com as Opções de Ocupado definidas para os usuários.
    
  - As chamadas não relacionadas à Chamada de Equipe para esses usuários serão aprididas pelas configurações de Opções de Ocupado.
    
- Delegação de chefe/administrador 
    
  - As chamadas de entrada para usuários que estão configuradas para delegação de chefe/administrador como chefe ou administrador serão priorizadas para ignorar as configurações de Ocupado quando Ocupado e Caixa Postal quando Ocupado.
    
  - A experiência atual de Delegação de Chefe/Administrador permanecerá inalterada com as Opções de Ocupado definidas para Administradores ou Chefe.
    
  - As chamadas não relacionadas à Delegação de Chefe/Administrador para Administradores serão acovadas pelas configurações de Opções de Ocupado.
    
- Aparência de linha compartilhada 
    
  - As configurações de Opções de Ocupado em contas de usuário configuradas para Aparência de Linha Compartilhada serão ignoradas. 
    
  - Em vez disso, as opções de Ocupado ocupado quando ocupado e caixa postal quando ocupado da Aparência de linha compartilhada serão a vontade.
    
- Serviço de Estacionamento de Chamada 
    
  - As chamadas estacionadas que não foram recuperadas e estão tocando de volta devido ao tempo final poderão tocar para o usuário que estacionou a chamada pelas Opções de Ocupado. 
    
- Conferência de Chamada
    
  - Os usuários em chamadas em conferência são considerados Ocupados e novas chamadas de entrada serão rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal de acordo com as configurações de Opções de Ocupado.
    
  - Os usuários em conferências não são impedidos de iniciar novas chamadas ou conferências por opções de ocupado.
    
  - Os usuários em conferências ainda podem receber novos convites de conferência, mas novas chamadas ponto a ponto serão rejeitadas de acordo com as configurações de Opções de Ocupado.
    
- Toque simultâneo e encaminhamento de chamada
    
    O recurso Ocupado quando Ocupado não foi projetado para funcionar com Toque Simultâneo e Encaminhamento de Chamada.
    

