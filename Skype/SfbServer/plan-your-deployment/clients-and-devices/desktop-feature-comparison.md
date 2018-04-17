---
title: Desktop client feature comparison for Skype for Business
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Summary: Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.'
ms.openlocfilehash: 0ce6457bea83c775ca5cf9373a5724f95785ddb1
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="desktop-client-feature-comparison-for-skype-for-business"></a>Desktop client feature comparison for Skype for Business
 
**Summary:** Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.
  
 Before you deploy or upgrade to Skype for Business, check which clients are already in use in your organization. Use the tables below to understand the feature support impact on those clients. Isso pode ajudar você a comunicar alterações aos usuários, a acompanhar o processo de implantação e a compreender totalmente os benefícios da atualização do cliente mais recente.
  
Some features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Online Admins may want to refer to [Skype for Business Online Service Description](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) for information on the different plans available to them.
  
The following tables show the features that are available with each client that works with Skype for Business Server 2015 or Skype for Business Online. You may also want to refer to [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md) for smart phone and tablet client feature comparisons. A Licença de Acesso para Cliente ou a Licença de Assinatura do Usuário que sua organização comprar também afetará os recursos que estarão disponíveis para os usuários. A implantação do cliente completo ou básico para os usuários dependerá da licença ou do plano que sua organização escolher comprar. See the [Licensing Guide](https://products.office.com/en-us/skype-for-business/it-pros) for more details.
  
> [!IMPORTANT]
> Skype for Business Server 2015 and Skype for Business Online support the following previously released clients: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition, and Lync 2010 Attendant. For information about these clients when used with other servers, see the [Client comparison tables for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) and [Client comparison tables for Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx). 
  
> [!NOTE]
> The **Lync 2010 Attendant** client is not supported in Skype for Business Online.
  
> [!NOTE]
> The Skype for Business Web App browser client and Skype Meetings App Windows 10 app only provide [Meetings support](desktop-feature-comparison.md#BKMK_Conferencing). Refer to [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) for more about these clients.
  
## <a name="enhanced-presence-support"></a>Suporte à Presença Avançada
<a name="BKMK_EnhancedPresence"> </a>

Esta tabela abrange os recursos de Presença Avançada que vão além de uma simples indicação de que o usuário está online, offline, ocupado, etc. 
  
|Recurso/funcionalidade|Cliente Skype for Business 2015 ou 2016|Skype for Business para Mac|Lync 2013 client|Aplicativo Lync Windows Store|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator para Mac 2011|Lync para Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Publicar status  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Exibir status  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir notas de status e mensagens de Ausência Temporária  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicionar um local personalizado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Adicionar uma nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Usar uma foto de qualquer site público para Minha Imagem  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||

 &#x2776;  Does not support publishing status based on calendar free/busy information.
  
## <a name="contacts-and-contact-groups-support"></a>Suporte para contatos e grupos de contatos
<a name="BKMK_Contacts"> </a>

Esta tabela abrange os recursos relacionados ao gerenciamento de contatos de IM e Presença. 
  

|Recurso/funcionalidade|Cliente Skype for Business 2015 ou 2016|Skype for Business para Mac | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Lista de Contatos pré-populada  <br/> |&#x2714;|||||||||
|Exibir e modificar a lista de contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Marcar contatos para alertas de alteração de status  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Controlar relações de privacidade  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Pesquisar o catálogo de endereços corporativo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pesquisar os contatos do Microsoft Outlook  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerenciar grupos de contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Expandir grupos de distribuição e Grupos do Office 365  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Pesquisar grupos de resposta  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Exibir o grupo de contatos recentes  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Exibir o grupo de conversas atuais  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Mostrar exibições de contatos alternativas (por exemplo, bloco)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Sort contacts by Group, Relationship, or New (people who've added you to their Contacts list)  <br/> |&#x2714;||&#x2714;|Classificar por grupo  <br/> |&#x2714;|&#x2714;||||
|Organizar contatos por status (disponibilidade)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Pesquisar e adicionar contatos do Exchange  <br/> |&#x2714;||&#x2714;||||||&#x2714;|
   
## <a name="im-support"></a>Suporte para mensagens instantâneas
<a name="BKMK_IMSupport"> </a>

Esta tabela abrange os recursos relacionados ao suporte a mensagens instantâneas.
  

|Recurso/funcionalidade | Cliente Skype for Business 2015 ou 2016 | Skype for Business para Mac | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensagens instantâneas ou enviar email para um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Navegar entre várias conversas de IM/acompanhar várias conversas em uma única janela com guias  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Registrar conversas de IM no Outlook  <br/> |&#x2714;|&#x2714;If server side conversation history is turned on  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Salvo no Communicator para Mac  <br/> |Salvo no Lync para Mac  <br/> |
|Usar modelos de conversa preparados  <br/> |||||&#x2714;|&#x2714;||||
|Verificar a ortografia  <br/> |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Skill search (with SharePoint Server integration)  <br/> (On-premises Skype for Business Server and on-premises SharePoint 2013 are required for skill search.)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integração de chat persistente (chat em grupo)  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Escalate a Persistent Chat room to a Skype for Business Meeting with one click  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Imagens embutidas do remetente e do destinatário na janela de IM  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Enviar mensagens à tinta  <br/> ||||&#x2714;||||||
|Receber mensagens à tinta  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Definir mensagens instantâneas com alta prioridade  <br/> |&#x2714;||&#x2714;|||||||
   
## <a name="meetings-support"></a>Suporte para reuniões
<a name="BKMK_Conferencing"> </a>

Esta tabela abrange os recursos relacionados ao suporte a reuniões.
  
> [!NOTE]
>  Skype for Business meeting features aren't available in Skype for Business Online Standalone Plan 1.

Nas sessões de Skype para Skype, um usuário do Skype for Business Online Plan 1 poderá participar do compartilhamento de área de trabalho e de compartilhamento de aplicativos se tiver sido convidado por um usuário que tem acesso aos recursos de compartilhamento.   
For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
|Recurso/funcionalidade | Skype for Business 2016 client | Skype for Business para Mac | Skype for Business Web App | Skype for Business 2015 client | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Adicionar áudio de computador  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicionar vídeo  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Exibir vídeo com vários participantes (modo de exibição de galeria)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Compartilhamento de tela baseado em vídeo  <br/> |&#x2714;|&#x2714;Only for users homed on Skype for Business Online  <br/> |&#x2714;View-only  <br/> |||||||||
|Usar os controles do apresentador na reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Acessar a lista de participantes detalhada da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Participar de IM com vários participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Compartilhar a área de trabalho (se habilitado)  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Compartilhar um programa (se habilitado)  <br/> |&#x2714;|Somente exibição  <br/> |&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;||||Somente exibição  <br/> |
|Adicionar participantes anônimos (se habilitado)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Usar reuniões de áudio discadas  <br/> |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Iniciar uma reunião do tipo Reunir Agora  <br/> |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Adicionar e apresentar arquivos do Microsoft PowerPoint  <br/> |&#x2714;| &#x2778; View only, annotations not available  <br/> |&#x2714;|&#x2714;|&#x2714;|Somente apresentação  <br/> |&#x2714;|||| &#x2778; View only, annotations not available  <br/> |
|Navegar por arquivos do Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Usar e editar notas de reunião do OneNote  <br/> |&#x2714;||Somente editar (sem adicionar)  <br/> |&#x2714;|&#x2714;|||||||
|Usar um quadro de comunicações  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Realizar votações  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Carregar arquivos para compartilhar com outras pessoas  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Agendar um reunião ou conferência  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook  <br/> ||||Outlook  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;|||||||||||
|Desabilitar vídeo de participante  <br/> |&#x2714;||&#x2714;|||||||||
|Desabilitar mensagens instantâneas de reunião  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Ativar mudo da audiência  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Tornar todos participantes  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Produzir Transmissão de Reunião do Skype  <br/> |&#x2714;|||||||||||
|O representante pode agendar uma reunião em nome do delegador  <br/> |&#x2714;|Apenas Skype for Business Online <br/>|&#x2714;|||||||||
|Sincronizar representantes entre o Skype for Business e o Outlook  <br/> |&#x2714;||&#x2714;|||||||||
|Compartilhamento de tela baseado em vídeo  <br/> |&#x2714;| Apenas Skype for Business Online <br/> |&#x2714;||&#x2714;|||||||
|Definir Destaque de Vídeo (bloquear vídeo)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Conceder/cancelar controle de compartilhamento de tela  <br/> |&#x2714;||&#x2714;|||||||||
   
 &#x2776;  Participants can't control desktops that are shared by Skype for Business on Mac, Lync for Mac 2011, or Communicator for Mac 2011 users. Skype for Business on Mac, Lync for Mac 2011 and Communicator for Mac 2011 users can't control desktops shared by Windows users. Isso também não funciona com o Skype for Business no Mac OSX.
  
 &#x2777;  For Skype for Business Online, this feature requires Microsoft PSTN Conferencing, Exchange Unified Messaging, or a 3rd party audio conferencing provider.
  
 &#x2778;  The Lync for Mac 2011 client cannot view Microsoft Office 2013 PowerPoint presentations when they have been shared in a conference by the Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>Suporte para voz (telefonia)
<a name="BKMK_Telephony"> </a>

Esta tabela abrange os recursos relacionados ao suporte a serviços de voz.
  
> [!NOTE]
> Skype for Business Voice (Telephony) features are limited to certain Skype for Business Online subscription plans. > For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
 | Recurso/funcionalidade | Cliente Skype for Business 2015 ou 2016 | Skype for Business para Mac | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar uma chamada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Clicar para ligar para um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir uma chamada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerenciar o encaminhamento de chamadas  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerenciar configurações de chamadas de equipe  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Gerenciar representantes  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU4 or later  <br/> |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Iniciar uma chamada para um Grupo de Resposta  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Suporte a serviços de emergência (E-911)  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU6 or later  <br/> |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to SIP URI(s) for E-911 call  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to distribution list for E-911 call  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Conectar-se à caixa postal, configurar ou alterar a saudação  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notificação de chamada perdida  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Realizar chamadas em nome de outro contato (cenário de gerente/representante)  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Atender chamadas de outras pessoas se configurado como representante  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Gerenciar grandes volumes de chamadas  <br/> |||||&#x2714;|&#x2714;||||
|Estacionamento de chamada  <br/> |&#x2714;||&#x2714; &#x2776; |||||||
|Recebimento de chamadas em grupo  <br/> |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Roteamento com base no local  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerenciar Grupo de chamada de equipe/Grupo de Resposta  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  This feature isn't available in Skype for Business Online.
  
## <a name="external-users-support"></a>Suporte para usuários externos
<a name="BKMK_ExternalUsers"> </a>

Esta tabela abrange os recursos relacionados ao suporte a usuários externos hospedados na PSTN.
  

|Recurso/funcionalidade | Cliente Skype for Business 2015 ou 2016 | Skype for Business para Mac | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM com um contato público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Iniciar IM com um contato federado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Realizar chamadas de dois ou vários participantes com usuários externos  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
## <a name="recording-support"></a>Suporte a gravação
<a name="BKMK_Recording"> </a>

Esta tabela abrange os recursos relacionados ao suporte à gravação de reuniões.
  
| Future/capability** | Cliente Skype for Business 2015 ou 2016 | Skype for Business para Mac | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Gravação de áudio e vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho e conteúdo carregado no lado do cliente  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Gravação de transferências de arquivos, páginas compartilhadas do OneNote e anotações do PowerPoint do lado do cliente  <br/> |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Selecionar a resolução de gravação preferencial  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  Recording is unavailable in certain Skype for Business Online standalone plans. A gravação exige direitos do cliente completo do Skype for Business.
  
 &#x2777;  Recording of file transfers, shared OneNote pages, and PowerPoint annotations is unavailable in Skype for Business Online.
  
## <a name="modern-authentication"></a>Autenticação moderna
<a name="BKMK_Recording"> </a>

Essa tabela abrange os recursos que precisam de suporte à autenticação moderna. 
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Recurso/funcionalidade | Cliente Skype for Business 2015 ou 2016 | Skype for Business para Mac | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticação moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticação multifator  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticação baseada em certificado  <br/> |&#x2714;(Domain-joined device only)  <br/> |&#x2714;|&#x2714;(Domain-joined device only)  <br/> |||||||
   
## <a name="archiving-compliance-and-logging-support"></a>Suporte a arquivamento, conformidade e logs
<a name="BKMK_Archiving"> </a>

Esta tabela abrange os recursos relacionados ao suporte a funções de arquivamento e registro em log.
  

 | Recurso/funcionalidade | Cliente Skype for Business 2015 ou 2016 | Skype for Business para Mac | Lync 2013 client | Aplicativo Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator para Mac 2011** | Lync para Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Arquivamento de conversas de IM no Histórico da Conversa do Outlook  <br/> |&#x2714; &#x2776; |&#x2714;If server side conversation history is turned on  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Salvo no Communicator para Mac  <br/> |Salvo no Lync para Mac  <br/> |
|Arquivamento do compartilhamento de áudio, vídeo e aplicativos, do compartilhamento de área de trabalho e do conteúdo carregado do lado do cliente  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Arquivamento de transferências de arquivos, páginas compartilhadas do OneNote e anotações do PowerPoint do lado do cliente  <br/> (unavailable in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|||||
|Access sign-in logs from Skype for Business icon in the task bar  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  For Skype for Business Online users, this feature requires Exchange Online and is controlled by the user's Exchange mailbox In-Place Hold attribute.
  
## <a name="client-limitations"></a>Limitações do cliente 
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitações do cliente básico
<a name="Full-Basic"> </a>

Os recursos a seguir estão disponíveis com o cliente completo e não estão disponíveis com o cliente básico:  
  
- Gerenciar configurações de chamada de equipe
    
- Gerenciar representantes
    
- Realizar chamadas em nome de outro contato (cenário de gerente/representante)
    
- Atender chamadas de outras pessoas se configurado como um representante
    
- Gerenciar volume alto de chamadas
    
- Iniciar uma chamada para um Grupo de Resposta
    
- Estacionamento de chamada
    
- Change greeting
    
- Recebimento de chamadas em grupo
    
### <a name="online-or-hybrid-user-account-limitations"></a>Limitações de conta de usuário online ou híbrida
<a name="Online-Hybrid"> </a>

As contas do usuário podem existir online ou no local e isso afetará os recursos que estarão disponíveis para aquele usuário. Users with accounts on Skype for Business Online will not have access to the following features, even with the Full client: 
  
- Presença avançada: usar uma foto de qualquer site público para Minha Imagem.
    
- Contatos: pesquisar grupos de resposta.
    
- Suporte para mensagens instantâneas: integração de chat persistente (chat em grupo).
    
- IM Support: Escalate a Persistent Chat room to a Skype for Business Meeting with one click
    
- Usuários externos: realizar chamadas de dois ou vários participantes com usuários externos.
    
## <a name="see-also"></a>Ver também
<a name="Types"> </a>

[Plan for clients and devices](clients-and-devices.md)

