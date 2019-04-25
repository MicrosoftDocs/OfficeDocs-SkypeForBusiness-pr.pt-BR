---
title: Configurando políticas para o Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuração de diretiva para Skype em ferramenta de desempenho e estresse do Business Server 2015.
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236160"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configurando políticas para o Skype para Business Server 2015 ferramenta de Stress e desempenho
 
Configuração de diretiva para Skype em ferramenta de desempenho e estresse do Business Server 2015.
  
Há várias políticas e outras áreas que você pode configurar no Skype para negócios 2015 do servidor, antes de executar a ferramenta de Stress e desempenho:
  
- [Política de arquivamento](configuring-policies.md#ArchivingPolicy)
    
- [Política de conferência](configuring-policies.md#ConferencingPolicy)
    
- [Política de contatos](configuring-policies.md#ContactsPolicy)
    
- [Política de Federação](configuring-policies.md#FederationPolicy)
    
- [Política de controle de admissão de chamada](configuring-policies.md#CACPolicy)
    
- [Regras de roteamento de voz](configuring-policies.md#VoiceRoutingRules)
    
- [Aplicativo Atendedor de conferência](configuring-policies.md#ConfAttendantApp)
    
- [Serviço estacionamento de chamada do servidor](configuring-policies.md#ServerCallParkServ)
    
- [Chamadas de emergência](configuring-policies.md#EmergencyCalls)
    
- [Configurando o aplicativo grupo de resposta](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Política de arquivamento
<a name="ArchivingPolicy"> </a>

Se você tiver um servidor de arquivamento implantado em sua Skype para topologia de servidores corporativos, você pode examinar o script ArchivingPolicy.ps1. Se você precisar de mais ajuda, confira os cmdlets de arquivamento e de webconferência.
  
## <a name="conferencing-policy"></a>Política de conferência
<a name="ConferencingPolicy"> </a>

Para conferências, temos o script MeetingPolicy.ps1. Se você precisar de mais ajuda, confira os cmdlets de webconferência.
  
## <a name="contacts-policy"></a>Política de contatos
<a name="ContactsPolicy"> </a>

Script de ContactsPolicy.ps1 será a amostra, que você precisará analisar. Os cmdlets IM e presença ajudará a se precisar de mais referências.
  
## <a name="federation-policy"></a>Política de Federação
<a name="FederationPolicy"> </a>

O script de exemplo para federação é FederationPolicy.ps1. Os cmdlets para revisar, se você precisar de mais insight, será o servidor de borda, Federação e acesso externo.
  
## <a name="call-admission-control-policy"></a>Política de controle de admissão de chamada
<a name="CACPolicy"> </a>

É possível fazer referência BandwidthPolicy.ps1 para esta diretiva. Os cmdlets de controle de admissão de chamada têm outras informações também.
  
## <a name="voice-routing-rules"></a>Regras de roteamento de voz
<a name="VoiceRoutingRules"> </a>

Você precisará o script de exemplo RoutingRules.ps1 para roteamento de voz. Quando você estiver configurando estas regras, tome nota do contexto de telefone (ou seja, /Location perfil ou /SimpleName) e os códigos de área interno ou externo, para que você possa especificá-los durante a criação de usuários. Você também precisará-los durante a configuração de LyncPerfTool (especificamente para UC-PSTN e UC-PSTN).
  
Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules.ps1 deve ser usado para o valor de LocationProfile na figura a seguir de UserProfileGenerator.exe:
  
![Skype para ferramenta de configuração de carga de negócios, guia de cenários de voz, as configurações avançadas de conversas.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Para obter detalhes, você pode revisar os cmdlets do Enterprise Voice.
  
## <a name="conference-attendant-application"></a>Aplicativo Atendedor de conferência
<a name="ConfAttendantApp"> </a>

Primeiro, revise o script ConferenceAutoAttendantConfiguration.ps1. Você vai querer tome nota do número de telefone ConferencingAutoAttendant (1121111111 por padrão), para que você pode inseri-lo na ferramenta de configuração de LyncPerfTool para geração de configuração, como a seguir:
  
![Os cenários de voz mostrando a carga de conferência nível da guia e número de telefone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Você encontrará mais detalhes na conferência discada e conferência cmdlets.
  
## <a name="server-call-park-service"></a>Serviço estacionamento de chamada do servidor
<a name="ServerCallParkServ"> </a>

Isso realmente é desabilitado por padrão. Você pode revisar o script de exemplo CallParkConfiguration.ps1 se precisar testar isso. Além disso, confira os cmdlets do aplicativo de estacionamento de chamada conforme necessário.
  
## <a name="emergency-calls"></a>Chamadas de emergência
<a name="EmergencyCalls"> </a>

Você precisará executar as seguintes etapas para configurar os testes para chamadas de emergência de desempenho e estresse:
  
1. Configure uma rota de voz para chamadas de emergência. Você pode usar o script RoutingRules.ps1 e verificar sob o comentário " **E911 rota para PSTN** " para obter um exemplo de como configurar esta rota de voz.
    
    > [!CAUTION]
    > O comando de exemplo no RoutingRules.ps1 tem um padrão de número que inclui o número 119 ao invés 911. Evite usar 911 (ou seu número de emergência local real) para evitar acidentais chamadas para os operadores de emergências locais durante seu teste de carga. Lembre-se de que essa configuração é apenas para fins de simulação! 
  
2. Configure endereços ao preencher os valores na guia **Configuração do serviço de informações de local** no UserProvisioningTool, conforme mostrado na figura a seguir:
    
     ![Ferramenta mostrando o número de endereços, sub-redes, comutadores e portas de provisionamento de usuário.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Quando você inseriu tudo para o UserProvisioningTool, clique no botão de **Gerar arquivos de configuração do LIS** .
    
4. Agora arquivos CSV para portas, sub-redes, comutadores e pontos de acesso sem fio (WAPs), bem como um arquivo XML para a ferramenta de Stress e desempenho será gerado. Você pode usar os arquivos CSV para entradas ao configurar o serviço de informações de local (LIS) com o script LisConfiguration.ps1. Para fazer isso, você precisará mover o arquivo de Locations0.xml na mesma pasta como a ferramenta de Stress e desempenho executável (LyncPerfTool.exe). Isso permitirá que você execute cenários (plano de discagem) de perfil de local.
    
## <a name="configuring-response-group-application"></a>Configurando o aplicativo grupo de resposta
<a name="ConfigResponseGroupApp"> </a>

O exemplo de script é ResponseGroupConfiguration.ps1. Também há cmdlets do aplicativo de grupo de resposta para analisar para obter mais detalhes de configuração. O diagrama a seguir mostrará alguns dos detalhes de configuração:
  
![Ferramenta de configuração de grupo de resposta mostrando os fluxos de trabalho existentes para o teste.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

