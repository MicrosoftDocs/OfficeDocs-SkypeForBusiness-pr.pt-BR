---
title: Configurando políticas para a ferramenta de stress e desempenho do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuração de política para a ferramenta de stress e desempenho do Skype for Business Server 2015.
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816190"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configurando políticas para a ferramenta de stress e desempenho do Skype for Business Server 2015
 
Configuração de política para a ferramenta de stress e desempenho do Skype for Business Server 2015.
  
Há várias políticas e outras áreas que você pode configurar no Skype for Business Server 2015, antes da execução da ferramenta de stress e desempenho:
  
- [Política de arquivamento](configuring-policies.md#ArchivingPolicy)
    
- [Política de conferência](configuring-policies.md#ConferencingPolicy)
    
- [Política de contatos](configuring-policies.md#ContactsPolicy)
    
- [Política de Federação](configuring-policies.md#FederationPolicy)
    
- [Política de controle de admissão de chamadas](configuring-policies.md#CACPolicy)
    
- [Regras de roteamento de voz](configuring-policies.md#VoiceRoutingRules)
    
- [Aplicativo de atendedor de conferência](configuring-policies.md#ConfAttendantApp)
    
- [Serviço de estacionamento de chamadas do servidor](configuring-policies.md#ServerCallParkServ)
    
- [Chamadas de emergência](configuring-policies.md#EmergencyCalls)
    
- [Configurando o aplicativo grupo de resposta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Política de arquivamento
<a name="ArchivingPolicy"> </a>

Se você tiver um servidor de arquivamento implantado na topologia do Skype for Business Server, poderá examinar o script ArchivingPolicy. ps1. Se precisar de mais assistência, confira os cmdlets Archiving e Webconferência.
  
## <a name="conferencing-policy"></a>Política de conferência
<a name="ConferencingPolicy"> </a>

Para a conferência, temos o script MeetingPolicy. ps1. Se precisar de mais assistência, confira os cmdlets da Webconferência.
  
## <a name="contacts-policy"></a>Política de contatos
<a name="ContactsPolicy"> </a>

O script ContactsPolicy. ps1 será o exemplo que você precisará revisar. Os cmdlets de presença e mensagens instantâneas ajudarão se você precisar de mais referências.
  
## <a name="federation-policy"></a>Política de Federação
<a name="FederationPolicy"> </a>

O script de exemplo para Federação é FederationPolicy. ps1. Os cmdlets a serem revisados, se você precisar de mais informações, será servidor de borda, Federação e acesso externo.
  
## <a name="call-admission-control-policy"></a>Política de controle de admissão de chamadas
<a name="CACPolicy"> </a>

Você pode fazer referência a BandwidthPolicy. ps1 para esta política. Os cmdlets do controle de admissão de chamadas também terão outras informações.
  
## <a name="voice-routing-rules"></a>Regras de roteamento de voz
<a name="VoiceRoutingRules"> </a>

Você precisará do script de exemplo RoutingRules. ps1 para roteamento de voz. Quando você estiver configurando essas regras, anote o contexto do telefone (ou seja, o perfil do/Location ou/SimpleName) e os códigos de área interna/externa, para que você possa especificá-los ao criar usuários. Você também precisará deles durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN).
  
Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules. ps1 deve ser usado para o valor LocationProfile na seguinte imagem do UserProfileGenerator. exe:
  
![Ferramenta de configuração de carregamento do Skype for Business, guia cenários de voz, configurações avançadas para conversas.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obter detalhes, você pode examinar os cmdlets do Enterprise Voice.
  
## <a name="conference-attendant-application"></a>Aplicativo de atendedor de conferência
<a name="ConfAttendantApp"> </a>

Primeiro, examine o script ConferenceAutoAttendantConfiguration. ps1. Você desejará anotar o número de telefone ConferencingAutoAttendant (1121111111 por padrão), para que possa inseri-lo na ferramenta de configuração LyncPerfTool para geração de configuração, como a seguir:
  
![A guia cenários de voz mostrando o nível de carga de conferência e o número de telefone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Você encontrará mais detalhes nos cmdlets de conferência discada e conferência.
  
## <a name="server-call-park-service"></a>Serviço de estacionamento de chamadas do servidor
<a name="ServerCallParkServ"> </a>

Isso, na verdade, é desabilitado por padrão. Você pode examinar o script de exemplo CallParkConfiguration. ps1 se precisar testá-lo. Além disso, confira os cmdlets do aplicativo de estacionamento de chamada conforme necessário.
  
## <a name="emergency-calls"></a>Chamadas de emergência
<a name="EmergencyCalls"> </a>

Você precisará executar as seguintes etapas para configurar o teste de carga e desempenho das chamadas de emergência:
  
1. Configurar uma rota de voz para chamadas de emergência. Você pode usar o script RoutingRules. ps1 e verificar abaixo do comentário " **Route E911 to PSTN** " para obter um exemplo de como configurar essa rota de voz.
    
    > [!CAUTION]
    > O comando de exemplo em RoutingRules. ps1 tem um padrão de número que inclui o número 119 em vez de 911. Você deve evitar usar o 911 (ou o seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga. Lembre-se que essa configuração é somente para fins de simulação! 
  
2. Para configurar endereços, preenchendo os valores na guia **configuração do serviço de informações de localização** no UserProvisioningTool, conforme mostrado na figura a seguir:
    
     ![Ferramenta de provisionamento de usuário mostrando o número de endereços, sub-redes, opções e portas.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Quando você tiver inserido tudo no UserProvisioningTool, clique no botão **GENERATE Lis config files** .
    
4. Agora, os arquivos CSV para portas, sub-redes, opções e pontos de acesso sem fio (WAPs), bem como um arquivo XML para a ferramenta stress e performance serão gerados. Você pode usar os arquivos CSV para entradas ao configurar o LIS (serviço de informações de localização) com o script LisConfiguration. ps1. Para fazer isso, você precisará mover o arquivo Locations0. xml para a mesma pasta que o executável da ferramenta de sobrecarga e de desempenho (LyncPerfTool. exe). Isso permitirá que você execute cenários de perfil de localização (plano de discagem).
    
## <a name="configuring-response-group-application"></a>Configurando o aplicativo grupo de resposta
<a name="ConfigResponseGroupApp"> </a>

O script de exemplo é ResponseGroupConfiguration. ps1. Também há cmdlets de aplicativo de grupo de resposta para analisar mais detalhes de configuração. O diagrama a seguir mostrará alguns dos detalhes de configuração:
  
![A ferramenta de configuração do grupo de resposta mostrando fluxos de trabalho existentes para teste.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

