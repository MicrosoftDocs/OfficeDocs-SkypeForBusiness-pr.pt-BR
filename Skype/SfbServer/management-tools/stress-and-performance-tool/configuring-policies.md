---
title: Configurando políticas para a Ferramenta de Stress and Performance do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Configuração de política para a Ferramenta de Stress and Performance do Skype for Business Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815031"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configurando políticas para a Ferramenta de Stress and Performance do Skype for Business Server 2015
 
Configuração de política para a Ferramenta de Stress and Performance do Skype for Business Server 2015.
  
Há várias políticas e outras áreas que você pode configurar no Skype for Business Server 2015, antes de executar a Ferramenta de Stress and Performance:
  
- [Política de arquivamento](configuring-policies.md#ArchivingPolicy)
    
- [Política de conferência](configuring-policies.md#ConferencingPolicy)
    
- [Política de contatos](configuring-policies.md#ContactsPolicy)
    
- [Política de federação](configuring-policies.md#FederationPolicy)
    
- [Política de Controle de Admissão de Chamada](configuring-policies.md#CACPolicy)
    
- [Regras de Roteamento de Voz](configuring-policies.md#VoiceRoutingRules)
    
- [Aplicativo Do Atendente de Conferência](configuring-policies.md#ConfAttendantApp)
    
- [Serviço Estacionamento de Chamada do Servidor](configuring-policies.md#ServerCallParkServ)
    
- [Chamadas de emergência](configuring-policies.md#EmergencyCalls)
    
- [Configurando o aplicativo Grupo de Resposta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Política de arquivamento
<a name="ArchivingPolicy"> </a>

Se você tiver um servidor de Arquivamento implantado em sua topologia do Skype for Business Server, poderá ver o ArchivingPolicy.ps1 script. Se precisar de mais ajuda, confira os cmdlets de Arquivamento e Webconferência.
  
## <a name="conferencing-policy"></a>Política de conferência
<a name="ConferencingPolicy"> </a>

Para conferência, temos o script MeetingPolicy.ps1 aplicativo. Se precisar de mais ajuda, confira os cmdlets de Webconferência.
  
## <a name="contacts-policy"></a>Política de contatos
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 script será o exemplo que você precisará analisar. Os cmdlets de IM e presença ajudarão se você precisar de mais referências.
  
## <a name="federation-policy"></a>Política de federação
<a name="FederationPolicy"> </a>

O script de exemplo para federação é FederationPolicy.ps1. Os cmdlets a serem revisados, se você precisar de mais informações, serão Servidor de Borda, federação e acesso externo.
  
## <a name="call-admission-control-policy"></a>Política de Controle de Admissão de Chamada
<a name="CACPolicy"> </a>

Você pode fazer referência BandwidthPolicy.ps1 para essa política. Os cmdlets de Controle de Admissão de Chamada também terão mais informações.
  
## <a name="voice-routing-rules"></a>Regras de Roteamento de Voz
<a name="VoiceRoutingRules"> </a>

Você precisará do script de RoutingRules.ps1 para Roteamento de Voz. Ao configurar essas regras, anote o contexto do telefone (ou seja, /Location Profile ou /SimpleName) e os Códigos de Área Interna/Externa para que você possa especificá-las ao criar usuários. Você também precisará deles durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN).
  
Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules.ps1 deve ser usado para o valor LocationProfile na seguinte figura de UserProfileGenerator.exe:
  
![Ferramenta de configuração de carga do Skype for Business, guia cenários de voz, Configurações avançadas para conversas.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obter detalhes, você pode revisar os cmdlets do Enterprise Voice.
  
## <a name="conference-attendant-application"></a>Aplicativo Do Atendente de Conferência
<a name="ConfAttendantApp"> </a>

Primeiro revise o ConferenceAutoAttendantConfiguration.ps1 script. Você vai querer anotar o número de telefone de ConferencingAutoAttendant (1121111111 por padrão), para que possa insira-o na ferramenta de configuração LyncPerfTool para geração de configuração, como abaixo:
  
![A guia Cenários de Voz mostrando o nível de Carga de Conferência e o número de telefone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Você encontrará mais detalhes nos cmdlets Conferência e Conferência Discada.
  
## <a name="server-call-park-service"></a>Serviço Estacionamento de Chamada do Servidor
<a name="ServerCallParkServ"> </a>

Na verdade, isso é desabilitado por padrão. Você pode revisar o CallParkConfiguration.ps1 script de exemplo se precisar testá-lo. Além disso, confira os cmdlets do Aplicativo de Estacionamento de Chamada conforme necessário.
  
## <a name="emergency-calls"></a>Chamadas de emergência
<a name="EmergencyCalls"> </a>

Você precisará executar as seguintes etapas para configurar testes de estresse e desempenho para chamadas de emergência:
  
1. Configurar uma rota de voz para chamadas de emergência. Você pode usar o script RoutingRules.ps1 e verificar sob o comentário " **Route E911 to PSTN** " para ver um exemplo de como configurar essa rota de voz.
    
    > [!CAUTION]
    > O comando de exemplo RoutingRules.ps1 tem um padrão de número que inclui o número 119 em vez de 911. Evite usar 911 (ou seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga. Lembre-se de que essa configuração é apenas para fins de simulação! 
  
2. Configure os endereços preenchendo os valores na guia **Configuração** do Serviço de Informações de Local no UserProvisioningTool, conforme mostrado na figura a seguir:
    
     ![Ferramenta de provisionamento do usuário mostrando o número de endereços, sub-redes, comutadores e portas.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Depois de ter inserido tudo no UserProvisioningTool, clique no **botão Gerar Arquivos de Configuração LIS.**
    
4. Agora, os arquivos CSV para portas, sub-redes, comutadores e WAPs (pontos de acesso sem fio), bem como um arquivo XML para a ferramenta Stress and Performance serão gerados. Você pode usar os arquivos CSV para entradas ao configurar o LIS (Serviço de Informações de Local) com o script LisConfiguration.ps1 local. Para fazer isso, você precisará mover o arquivo Locations0.xml para a mesma pasta que o executável da Ferramenta de Stress and Performance (LyncPerfTool.exe). Isso permitirá que você execute cenários de perfil de local (plano de discagem).
    
## <a name="configuring-response-group-application"></a>Configurando o aplicativo Grupo de Resposta
<a name="ConfigResponseGroupApp"> </a>

O script de exemplo é ResponseGroupConfiguration.ps1. Também há cmdlets de aplicativo do Grupo de Resposta para revisar para obter mais detalhes de configuração. O diagrama a seguir mostrará alguns dos detalhes da configuração:
  
![A ferramenta de configuração do Grupo de Resposta mostrando fluxos de trabalho existentes para teste.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

