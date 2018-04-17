---
title: Mobile client feature comparison for Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Summary: Review the feature support for the mobile client while planning for Skype for Business Server 2015.'
ms.openlocfilehash: 4287c5baf0642fab9d55d291470b2352f3da5932
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Mobile client feature comparison for Skype for Business
 
**Summary:** Review the feature support for the mobile client while planning for Skype for Business Server 2015.
  
This article compares the features and capabilities among Skype for Business mobile clients and the Skype for Business desktop client in the following categories:
  
- Conexão, notificações por push e recursos gerais
    
- Presença avançada
    
- Contatos e grupos de contato
    
- IM (sistema de mensagens instantâneas)
    
- Skype for Business to Skype for Business audio and video
    
- Conferência
    
- Telefonia
    
- Usuários externos
    
- Arquivamento e conformidade
    
-  Autenticação moderna
    
The following tables list the features that are available to Skype for Business users in an on-premises deployment of Skype for Business Server 2015. The same features are also available to Skype for Business Online and Microsoft Office 365 users, unless otherwise indicated in the table footnotes.
  
> [!NOTE]
> For online help and resources for end users, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> To compare the features available in other Skype for Business clients, see [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md). 
  
## <a name="sign-in-push-notifications-and-general-features"></a>Conexão, notificações por push e recursos gerais

 
 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business session remains signed in  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Suporte para notificações de push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714;|&#x2714;|
|As informações de conta de vários usuários podem ser armazenadas em cache no mesmo dispositivo  <br/> |&#x2714;||||
|Leitor de tela/voice over  <br/> |&#x2714;|&#x2714; &#x2777;           English only  <br/> |&#x2714;|&#x2714;|
|Use um teclado externo para acessibilidade  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Apoio ao Programa de Aperfeiçoamento da Experiência do Usuário  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  On Windows Phone, Skype for Business signs out automatically after a period of inactivity, as follows:
  
- If the user has enabled push notifications, Skype for Business signs out after 10 days of inactivity.
    
- If the user has not enabled push notifications, Skype for Business signs out as soon as the user leaves the app.
    
On iOS devices, Skype for Business signs out automatically after the mobile client has not contacted the server for 10 days due to loss of network connectivity or other issues.
  
 &#x2777;  In app only.
  
 &#x2778;  Notifications are available when the app is running in the background.
  
## <a name="enhanced-presence-support"></a>Suporte para presença avançada


 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar e exibir status  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir status com base nas informações de disponibilidade de calendário  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir notas de status e mensagens de Ausência Temporária  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicionar um local personalizado  <br/> |&#x2714;||||
|Adicionar uma nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publicar status com base na informação de disponibilidade do calendário   <br/> |&#x2714; &#x2776; ||||
|Definir estado de presença manual (como Ocupado, Não Incomodar e assim por diante)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Skype for Business mobile clients do not update a user's presence based on the user's free/busy calendar information. If a mobile client user is also signed in to the Skype for Business desktop client, the desktop client updates the user's presence based on the user's free/busy calendar information. If the user is signed in to a mobile client only, the user's presence does not update based on free/busy calendar information.
  
## <a name="contacts-and-contact-groups-support"></a>Suporte para contatos e grupos de contatos


 | Recurso/capacidade  | Skype for Business Lync 2013 desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Exibir lista de contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir grupos de contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir grupos de contatos frequentes  <br/> |&#x2714;||||
|Modificar lista de contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Marcar contatos para alertas de alteração de status  <br/> |&#x2714;||||
|Controlar relações de privacidade  <br/> |&#x2714;||||
|Pesquisar o catálogo de endereços corporativo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pesquisar lista de contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gerenciar grupos de contatos  <br/> |&#x2714;|||&#x2714;|
|Expandir grupos de distribuição  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Pesquisar grupos de resposta  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Exibir ou ocultar fotos do contato  <br/> |&#x2714;|&#x2714;|||
|Fixe um contato em sua tela inicial  <br/> ||&#x2714;|||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="instant-messaging-support"></a>Suporte ao sistema de mensagens instantâneas


 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM (sistema de mensagens instantâneas) com um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar de IM com vários participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar outros por uma janela de conversa  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir conversas atuais  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar entre várias conversas de IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Fazer o login automaticamente de conversas de IM no Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Enviar uma conversa de IM como uma mensagem de email  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar um email para um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir convites de IM perdidos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrar com IM em entrada  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776;  This device vibrates every time an IM is received even if the current message in the IM conversation is displayed
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business to Skype for Business audio and video


 | Recurso/funcionalidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-to-Skype for Business voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-to-Skype for Business video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Por padrão, o vídeo em um dispositivo móvel requer uma conexão Wi-Fi.  
  
## <a name="conferencing-support"></a>Suporte a conferências


 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clicar em um link no lembrete de reunião para participar de uma reunião com vídeo ou VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar de IM com vários participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar a conferência discada (o servidor chama o dispositivo móvel)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar conferência de áudio discada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir vídeo da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir vídeo com vários participantes (modo de exibição de galeria)  <br/> |&#x2714;||||
|Aguardar no lobby da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar os controles do apresentador na reunião  <br/> |&#x2714;||||
|Acessar lista de participação da reunião detalhada para conferências de áudio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Acessar lista de participação da reunião detalhada para conferências de IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhar área de trabalho ou programa  <br/> |&#x2714;||||
|View shared desktop or program (VbSS or RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Exibir arquivos compartilhados do PowerPoint  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Carregar e apresentar arquivos do PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usar ferramentas de reunião (usar quadro de comunicações, conduzir votações, compartilhar arquivos)  <br/> |&#x2714;||||
|Navegar por uma lista de suas reuniões  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Join a meeting even if you don't have a Skype for Business account  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualize mais informações sobre os participantes da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inicie uma conversa de grupo não agendada com vários participantes diretamente de seu cliente ou dispositivo   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  For Office 365 users, this feature requires Enterprise Voice, which is part of the E5 license.
  
 &#x2777;  Requires a WiFi connection by default.
  
## <a name="telephony-support"></a>Suporte a telefonia


 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for Business, tap the call icon to call a contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir uma chamada  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transferência consultiva  <br/> |&#x2714; &#x2778; ||||
|Gerenciar o encaminhamento de chamadas  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gerenciar configurações de chamadas de equipe  <br/> |&#x2714; &#x2776; ||||
|Gerenciar representantes  <br/> |&#x2714; &#x2776; ||||
|Iniciar uma chamada para um Grupo de Resposta  <br/> |&#x2714; &#x2776; ||||
|Serviços de suporte a emergências  <br/> |&#x2714; &#x2777; ||||
|Realizar chamadas em nome de outro contato (cenário de gerente/representante)  <br/> |&#x2714; &#x2776; ||||
|Handle another contact's calls, if configured as a delegate  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Use Telefonar via Trabalho   <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Acessar caixa postal  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use the keypad in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776;  Available to Skype for Business Online and/or Office 365 E5 users, and users homed on Skype for Business Server 2015 or Lync 2013 with Enterprise Voice enabled.
  
 &#x2777;  For Skype for Business Online and/or Office 365 users, this feature is supported by Microsoft partners.
  
 &#x2778;  Windows Desktop client only.
  
## <a name="external-user-support"></a>Suporte a usuários externos


 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM com um contato público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar IM com um contato federado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Conduzir chamadas de duas partes com usuários externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Conduzir chamadas de várias partes com usuários externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work to reach a federated contact on their mobile phone by calling their published work number  &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  By default, federated users are assigned the External Contacts privacy relationship. Para que seja possível chamar um contato federado em seu telefone celular ligando para seu número comercial publicado, o contato federado deve atribuir manualmente a você a relação de privacidade Colegas.
  
## <a name="address-book-integration"></a>Integração do catálogo de endereços


 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Ligar para contatos do catálogo de endereços do dispositivo  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Make Skype for Business calls to contacts directly from device address book  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Suporte a arquivamento e conformidade


 | Recurso/capacidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Oferece arquivamento no lado do cliente  <br/> |&#x2714;||||
|Oferece gravação no lado do cliente  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="modern-authentication"></a>Autenticação moderna

Essa tabela abrange os recursos que precisam de suporte à autenticação moderna.
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Recurso/funcionalidade  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticação moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticação multifator  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticação baseada em certificado  <br/> |&#x2714;(Domain-joined device only)  <br/> ||&#x2714;|&#x2714;|
|Mobile Application Management (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

