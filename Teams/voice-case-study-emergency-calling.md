---
title: Estudo de caso do Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785945"
---
# <a name="contoso-case-study-emergency-calling"></a>Estudo de caso da Contoso: Chamada de emergência

Para entender a disponibilidade de chamada de emergência e terminologia relacionadas a chamada de emergência, Endereço, Local, Localização de Emergência e Endereço Registrado, a Contoso revisou Gerenciar chamada e plano de emergência e configurou uma chamada de emergência &mdash; &mdash; [dinâmica.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)

No Office 365, um usuário do Plano de Chamada é habilitado automaticamente para chamada de emergência. Mas somente usuários do Plano de Chamada nos Estados Unidos podem usar locais dinâmicos para rotear chamadas de emergência. 

Para o Roteamento Direto, a Contoso aprendeu que é necessária uma configuração adicional para o roteamento de chamadas de emergência e possivelmente para a conectividade do parceiro. O administrador deve configurar a conexão com um ERSP (Provedor de Serviços de Roteamento de Emergência) (Estados Unidos) OU configurar o Controlador de Borda de Sessão (SBC) para um aplicativo ELIN (Número de Identificação de Localização de Emergência).

A Contoso tem escritórios nos Estados Unidos e fora dos Estados Unidos:

- Nos Estados Unidos, os usuários do Plano de Chamada da Contoso podem usar locais dinâmicos para rotear chamadas de emergência. 

- Fora dos Estados Unidos, a Contoso tem alguns sites que usam Planos de Chamada e alguns sites conectados ao Sistema de Telefonia por meio do Roteamento Direto.

## <a name="emergency-calling-use-cases"></a>Casos de uso de chamada de emergência

Depois de decidir como a Contoso se conectará ao sistema telefônico, a Contoso identificou os seguintes casos de uso de chamadas de emergência: 

- [Usuário do Plano de Chamada nos Estados Unidos](#calling-plan-user-in-the-united-states) 

- [Usuário do Plano de Chamada fora dos Estados Unidos](#calling-plan-user-outside-of-the-united-states)

- [Usuário que se conecta ao Sistema telefônico por meio de Roteamento Direto](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Usuário do Plano de Chamada nos Estados Unidos  

Há requisitos para quando o número de telefone precisa estar associado a um local de emergência. Para entender esses requisitos, a Contoso [reviu Considerações sobre Planos de Chamada.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

Com base nesses requisitos, a Contoso decidiu associar o local ao número de telefone quando um número é atribuído a um usuário nos Estados Unidos.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Usuário do Plano de Chamada fora dos Estados Unidos 

Para entender quando um número de telefone precisa ser associado a um local de emergência, a Contoso revisões considerações [sobre planos de chamada.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) Com base nos requisitos, a Contoso decidiu o seguinte:  

-  A Contoso associará o local ao número de telefone quando um número for atribuído a um usuário no Canadá. 

- A Contoso atribuirá um local de emergência quando o número de telefone for adquirido do Office 365 ou quando um número for transferido de outro provedor de serviços ou operadora. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Usuário que se conecta ao Sistema telefônico por meio de Roteamento Direto 

Para planejar o roteamento de emergência para esse caso de uso, a Contoso [revisou Considerações sobre Roteamento Direto.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) Como os usuários do Roteamento Direto não recebem chamadas de emergência da mesma maneira que os usuários do Plano de Chamada, a Contoso teve que decidir como fazer chamadas de emergência. O Roteamento Direto pode ser conectado a um ERSP (Provedor de Serviços de Roteamento de Emergência). O Roteamento Direto também pode ter um SBC que inclui um ELIN (Número de Identificação de Localização de Emergência).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Considerações sobre o PROVEDOR de Serviços de Roteamento de Emergência (ERSP)

Os ERSPs (Provedores de Serviços de Roteamento de Emergência) podem rotear automaticamente chamadas de emergência com base na localização do chamador.  

- Se um Provedor de Serviços de Roteamento de Emergência estiver integrado a uma implantação de Roteamento Direto, as chamadas de emergência com um local adquirido dinamicamente serão automaticamente roteada para o PSAP (Ponto de Atendimento de Segurança Pública) que atende a esse local. 

- As chamadas de emergência sem um local adquirido dinamicamente são primeiramente teladas para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado. 


#### <a name="elin-considerations"></a>Considerações sobre OLIN

Se um aplicativo ELIN SBC estiver integrado a uma implantação de Roteamento Direto, etapas de configuração adicionais precisarão ocorrer para associar os endereços de emergência aos números de telefone.  

A Contoso decidiu usar controladores de borda de sessão que incluem aplicativos ELIN (Número de Identificação de Localização de Emergência).  

## <a name="security-desk-notification"></a>Notificação de segurança

A capacidade de notificar a central de segurança quando uma chamada de emergência é feita está disponível para os Planos de Chamada da Microsoft e o Roteamento Direto do Sistema de Telefonia. A Contoso revisou os detalhes na notificação de Segurança para determinar se isso deve ser configurado em seus escritórios  

A Contoso decidiu usar a notificação de segurança.

## <a name="configuration"></a>Configuração 

A Contoso seguiu as etapas em [Configurar chamada de emergência dinâmica](configure-dynamic-emergency-calling.md) para: 

- Atribuir endereços de emergência 

- Definir configurações de rede 

- Configurar o Serviço de Informações de Localização 

- Configurar políticas de emergência 

- Habilitar usuários e sites 

- Testar chamada de emergência 

Após a configuração de chamada de emergência dinâmica, a Contoso precisa atribuir o local ao usuário apropriado.  

- Para adicionar, alterar ou remover um local de emergência para sua organização, a Contoso seguiu as etapas em [Adicionar,](add-change-remove-emergency-location-organization.md) alterar ou remover um local de emergência para sua organização

- Para criar locais para edifícios, andares e escritórios, a Contoso seguiu as etapas em Adicionar, alterar ou remover um local para um local [de emergência.](add-change-remove-emergency-place-organization.md) 

- Para atribuir um local de emergência, a Contoso seguiu as etapas em [Atribuir ou alterar um local de emergência para um usuário.](assign-change-emergency-location-user.md) 

 