---
title: Estudo de caso da Contoso Voice Teams
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
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785945"
---
# <a name="contoso-case-study-emergency-calling"></a>Estudo de caso da Contoso: chamadas de emergência

Para entender a disponibilidade de chamadas de emergência e terminologia relacionada ao endereço de emergência de chamada de emergência &mdash; , lugar, local de emergência e endereço cadastrado, a &mdash; contoso revisou [gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md) e [planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).

No Office 365, um usuário do plano de chamada é habilitado automaticamente para chamadas de emergência. Mas somente os usuários de plano de chamada nos Estados Unidos podem usar locais dinâmicos para direcionar as chamadas de emergência. 

Para direcionamento direto, a contoso aprendeu que uma configuração adicional é necessária para roteamento de chamadas de emergência e possivelmente para conectividade de parceiros. O administrador deve configurar a conexão para um provedor de serviços de roteamento de emergência (ERSP) (Estados Unidos) ou configurar o controlador de borda de sessão (SBC) para um aplicativo de número de identificação de localização de emergência (ELIN).

A contoso tem escritórios nos Estados Unidos e fora dos Estados Unidos:

- Nos Estados Unidos, os usuários do plano de chamadas da Contoso podem usar locais dinâmicos para direcionar as chamadas de emergência. 

- Fora dos Estados Unidos, a contoso tem alguns sites que usam planos de chamadas e alguns sites conectados ao sistema telefônico por meio de roteamento direto.

## <a name="emergency-calling-use-cases"></a>Casos de uso de chamadas de emergência

Depois de decidir como a contoso se conectará ao sistema telefônico, a contoso identificou os seguintes casos de uso de chamadas de emergência: 

- [Usuário do plano de chamada nos Estados Unidos](#calling-plan-user-in-the-united-states) 

- [Plano de chamada usuário fora dos Estados Unidos](#calling-plan-user-outside-of-the-united-states)

- [Usuário que se conecta ao sistema telefônico por meio do roteamento direto](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Usuário do plano de chamada nos Estados Unidos  

Há requisitos para quando o número de telefone precisa estar associado a um local de emergência. Para compreender esses requisitos, a contoso revisou as [considerações para planos de chamada](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans). 

Com base nesses requisitos, a Contoso decidiu associar o local ao número de telefone quando um número é atribuído a um usuário nos Estados Unidos.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Plano de chamada usuário fora dos Estados Unidos 

Para entender quando um número de telefone precisa estar associado a um local de emergência, a contoso revisou as [considerações para planos de chamada](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans). Com base nos requisitos, a Contoso decidiu o seguinte:  

-  A contoso associará o local ao número de telefone quando um número for atribuído a um usuário no Canadá. 

- A contoso atribuirá um local de emergência quando o número de telefone for adquirido do Office 365 ou quando um número for transferido de outro provedor de serviços ou operadora. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Usuário que se conecta ao sistema telefônico por meio do roteamento direto 

Para planejar o roteamento de emergência para esse caso de uso, a contoso revisou as [considerações para roteamento direto](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing). Como os usuários de roteamento direto não recebem chamadas de emergência da mesma maneira que os usuários do plano de chamadas, a Contoso tinha que decidir como fazer chamadas de emergência. O roteamento direto pode ser conectado a um provedor de serviços de roteamento de emergência (ERSP). O roteamento direto também pode ter um SBC que inclui um número de identificação de localização de emergência (ELIN).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Considerações sobre o provedor de serviços de roteamento de emergência (ERSP)

Os provedores de serviços de roteamento de emergência (ERSPs) podem rotear automaticamente as chamadas de emergência com base na localização do chamador.  

- Se um provedor de serviços de roteamento de emergência estiver integrado a uma implantação de roteamento direto, as chamadas de emergência com um local adquirido dinamicamente serão automaticamente roteadas para o ponto de resposta de segurança pública (PSAP) que está servindo essa localização. 

- As chamadas de emergência sem um local adquirido dinamicamente são organizadas em primeiro lugar para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado. 


#### <a name="elin-considerations"></a>Considerações sobre o ELIN

Se um aplicativo ELIN do SBC estiver integrado a uma implantação de roteamento direto, etapas de configuração adicionais precisarão ocorrer para associar os endereços de emergência a números de telefone.  

A Contoso decidiu usar os controladores de borda de sessão que incluem aplicativos de número de identificação de local de emergência (ELIN).  

## <a name="security-desk-notification"></a>Notificação de segurança técnica

A capacidade de notificar a mesa de segurança quando uma chamada de emergência é feita está disponível para planos de chamadas da Microsoft e roteamento direto do sistema telefônico. A contoso revisou os detalhes na notificação de segurança para determinar se isso deve ser configurado em seus escritórios  

A Contoso decidiu usar a notificação de segurança técnica.

## <a name="configuration"></a>Configuração 

A contoso seguiu as etapas em [Configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md) para: 

- Atribuir endereços de emergência 

- Definir configurações de rede 

- Configurar o serviço de informações de localização 

- Configurar políticas de emergência 

- Habilitar usuários e sites 

- Testar chamadas de emergência 

Após a configuração da chamada de emergência dinâmica, a contoso precisava atribuir o local ao usuário adequado.  

- Para adicionar, alterar ou remover um local de emergência de sua organização, a contoso seguiu as etapas em [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)

- Para criar locais para edifícios, andares e escritórios, a contoso seguiu as etapas em [Adicionar, alterar ou remover um local para um local de emergência](add-change-remove-emergency-place-organization.md) . 

- Para atribuir um local de emergência, a contoso seguiu as etapas em [atribuir ou alterar um local de emergência para um usuário](assign-change-emergency-location-user.md). 

 