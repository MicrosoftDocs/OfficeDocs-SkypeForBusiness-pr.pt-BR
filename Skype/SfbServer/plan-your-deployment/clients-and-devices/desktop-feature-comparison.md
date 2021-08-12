---
title: Comparação de recursos do cliente de área de trabalho Skype for Business Server 2015
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Resumo: Skype for Business Server 2015 ou Skype for Business online podem usar essas tabelas para entender quais recursos são suportados em quais clientes.'
ms.openlocfilehash: c3c7e8a744f678a1453c52f57f7d97ae96cb0588cf6bc416ad04007a35eeba6f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318814"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Comparação de recursos do cliente de área de trabalho Skype for Business Server 2015

**Resumo:** Skype for Business Server 2015 ou Skype for Business online podem usar essas tabelas para entender quais recursos são suportados em quais clientes.
  
 Antes de implantar ou atualizar para Skype for Business, verifique quais clientes já estão em uso em sua organização. Use as tabelas abaixo para entender o impacto do suporte a recursos nesses clientes. Isso pode ajudá-lo a comunicar alterações aos usuários, a acompanhar o processo de lançamento e a entender totalmente os benefícios da atualização para o cliente mais recente.
  
Alguns recursos disponíveis com o Skype for Business Server 2015 não estão disponíveis no Skype for Business Online, consulte Online ou [Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Os administradores online podem querer se referir [Skype for Business Descrição](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description) do Serviço Online para obter informações sobre os diferentes planos disponíveis para eles.

Consulte Comparação de recursos do cliente da área de [trabalho Skype for Business 2019](../../../SfBServer2019/plan/feature-comparison.md) para suporte ao cliente Skype for Business Server 2019.
  
As tabelas a seguir mostram os recursos que estão disponíveis com cada cliente que trabalha com Skype for Business Server 2015 ou Skype for Business Online. Você também pode querer se referir à [comparação](mobile-feature-comparison.md) de recursos do cliente móvel para Skype for Business para comparações de recursos de cliente de smartphone e tablet. A Licença de Acesso para Cliente ou Licença de Assinatura de Usuário que sua organização compra também terá um impacto sobre quais recursos estão disponíveis para seus usuários. Se você implantar o cliente Completo ou Básico para os usuários depende da licença ou do plano que sua organização opta por comprar. Consulte o [Guia de Licenciamento](https://products.office.com/skype-for-business/it-pros) para obter mais detalhes.
  
> [!IMPORTANT]
> Skype for Business Server 2015 e Skype for Business Online suportam os seguintes clientes lançados anteriormente: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Telefone Edition e Lync 2010 Attendant. Para obter informações sobre esses clientes quando usados com outros servidores, consulte as tabelas de comparação de cliente do [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-desktop-client-comparison-tables) e tabelas de comparação de cliente do [Lync Server 2010](/previous-versions/office/skype-server-2010/gg425836(v=ocs.14)).

> [!NOTE]
> O **cliente do Lync 2010 Attendant** não tem suporte no Skype for Business Online.

> [!NOTE]
> O Skype for Business Web App do navegador e o aplicativo Skype reuniões Windows 10 apenas oferecem [suporte a Reuniões.](desktop-feature-comparison.md#BKMK_Conferencing) Consulte [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) para saber mais sobre esses clientes.
  
## <a name="enhanced-presence-support"></a>Suporte a presença aprimorado

<a name="BKMK_EnhancedPresence"> </a>

Esta tabela aborda os recursos de Presença Aprimorada que vão além de uma simples indicação de se um usuário está online, offline, ocupado, etc.
  
|Recurso/funcionalidade|Skype for Business cliente 2015 ou 2016|Skype for Business no Mac|Cliente Lync 2013|Aplicativo do Lync Windows Store|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator para Mac 2011|Lync para Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Status de publicação |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Exibir status   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exiba as notas de status e as mensagens Fora do Escritório |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicione um local personalizado |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Adicione uma nota personalizada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Use uma foto de qualquer site público para Minha Imagem (não disponível no Skype for Business Online) |&#x2714;||&#x2714;|||||||

 &#x2776; Não dá suporte ao status de publicação com base nas informações de agenda de livre/ocupado.
  
## <a name="contacts-and-contact-groups-support"></a>Suporte a contatos e grupos de contatos

<a name="BKMK_Contacts"> </a>

Esta tabela aborda os recursos relacionados ao gerenciamento de contatos de IM e Presença.

|Recurso/funcionalidade|Skype for Business cliente 2015 ou 2016|Skype for Business no Mac | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Lista de contatos pré-preenchidos |&#x2714;|||||||||
|Exibir e modificar lista de contatos |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Marque os contatos para alertas de alteração do status |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Controle as relações de privacidade |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Pesquise na agenda corporativa |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pesquise os contatos do Microsoft Outlook |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerencie os grupos de contatos |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Expandir grupos de distribuição e grupos Microsoft 365 grupos |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Pesquise os Grupos de Respostas  <br/> (não disponível no Skype for Business Online) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Exiba o grupo de contatos recentes |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Exiba o grupo de conversas atuais |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Mostre as exibições de contato alternativas (por exemplo, lado a lado) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Classificar contatos por Grupo, Relação ou Novo (pessoas que adicionaram você à lista de contatos) |&#x2714;||&#x2714;|Classificar por grupo |&#x2714;|&#x2714;||||
|Classificar contatos por Status (disponibilidade) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Pesquisar e adicionar Exchange contatos |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>Suporte a IM

<a name="BKMK_IMSupport"> </a>

Esta tabela aborda recursos relacionados ao suporte a IM.

|Recurso/funcionalidade | Skype for Business cliente 2015 ou 2016 | Skype for Business no Mac | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM com ou email para um contato |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Navegue entre várias conversas de IM/Rastrear várias conversas em uma única janela de tabulação |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Registre as conversas de IM no Outlook |&#x2714;|&#x2714;Se o histórico de conversas do lado do servidor estiver ligado  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Salvo no Communicator para Mac |Salvo no Lync para Mac |
|Use modelos de conversa preparados |||||&#x2714;|&#x2714;||||
|Verificar ortografia |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Pesquisa de habilidades (com a integração SharePoint Server)  <br/> (O Skype for Business Server local e o SharePoint 2013 são necessários para pesquisa de habilidades.) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integração de Chat Persistente (Chat de Grupo)  <br/> (não disponível para Skype for Business Online) |&#x2714;||&#x2714;|||||||
|Escalonar uma sala de Chat Persistente para uma reunião Skype for Business com um clique  <br/> (não disponível para Skype for Business Online) |&#x2714;||&#x2714;|||||||
|Imagens em linha do remetente e do receptor na janela de IM |&#x2714;||&#x2714;|&#x2714;||||||
|Enviar mensagens de tinta ||||&#x2714;||||||
|Receber mensagens de tinta |&#x2714;||&#x2714;|&#x2714;||||||
|Definir mensagens de mensagens IM como de alta importância |&#x2714;||&#x2714;|||||||
|Transferir arquivos em conversas de IM ponto a ponto |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>Suporte a reuniões

<a name="BKMK_Conferencing"> </a>

Esta tabela aborda recursos relacionados ao suporte a Reuniões.
  
> [!NOTE]
> Skype for Business recursos de reunião não estão disponíveis no Skype for Business Online Standalone Plan 1.  O Plano 1 está sendo [retirado.](../../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement.md)

Em Skype de Skype, um usuário do plano 1 do Skype for Business Online poderá participar do compartilhamento de aplicativos e compartilhamento de área de trabalho se for convidado por um usuário que tenha acesso aos recursos de compartilhamento.
Para obter detalhes, consulte o [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).
  
|Recurso/funcionalidade | Skype for Business cliente 2016 | Skype for Business no Mac | Skype for Business Web App | Skype for Business cliente 2015 | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Adicione áudio de computador |&#x2714;|&#x2714;|&#x2714;(requer plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicione vídeo |&#x2714;|&#x2714;|&#x2714;(requer plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Exibir vídeo de várias partes (modo de exibição de galeria) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Compartilhamento de tela baseado em vídeo |&#x2714;|&#x2714;|&#x2714;somente exibição |||||||||
|Use controles de apresentador durante a reunião |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Acesse a lista da reunião detalhada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Participe de IM com várias partes |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Compartilhe a área de trabalho (se ativado) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requer plug-in) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Compartilhe um programa (se ativado) |&#x2714;|Somente exibição   |&#x2714;(requer plug-in) |&#x2714;|&#x2714;||&#x2714;||||Somente exibição |
|Adicione participantes anônimos (se ativado) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Usar reuniões de áudio discado |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Iniciar uma reunião do Meet Now |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Adicione e apresente arquivos do Microsoft PowerPoint |&#x2714;| &#x2778; Anotações não disponíveis |&#x2714;|&#x2714;|&#x2714;|Somente presente |&#x2714;|||| &#x2778; exibir somente, anotações não disponíveis |
|Navegar nos arquivos PowerPoint Microsoft |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Adicionar e editar OneNote de reunião |&#x2714;||Editar somente (não adicionar) |&#x2714;|&#x2714;|||||||
|Use um quadro de avisos |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Faça votações |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Upload arquivos para compartilhar com outras pessoas |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Programe uma reunião ou conferência |Outlook ou Agendador do Skype for Business Web |Outlook ou Agendador do Skype for Business Web |Agendador do Skype for Business Web |Outlook ou Agendador do Skype for Business Web |Outlook ou Agendador da Web do Lync |Outlook ou Agendador da Web do Lync |Outlook ||||Outlook |
|Q &amp; A Manager |&#x2714;|||||||||||
|Desabilitar o vídeo do participante|&#x2714;||&#x2714;|||||||||
 | |Desabilitar o IM de reunião  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Mute Audience   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Tornar todos participantes |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Produzir Reunião do Skype Transmissão  |&#x2714;|||||||||||
|O representante pode agendar uma reunião em nome do representante  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Sincronizar representantes entre Skype for Business e Outlook |&#x2714;||&#x2714;|||||||||
|Definir destaque de vídeo (vídeo de bloqueio) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Dar/assumir o controle do compartilhamento de tela |&#x2714;||&#x2714;|||||||||

 &#x2776; Participantes não podem controlar áreas de trabalho compartilhadas pelo Skype for Business no Mac, no Lync para Mac 2011 ou no Communicator para usuários do Mac 2011. Skype for Business mac, Lync para Mac 2011 e Communicator para mac 2011 usuários não podem controlar áreas de trabalho compartilhadas por usuários Windows. Isso também não funcionará para Skype for Business Web App no Max OSX.
  
 &#x2777; Para Skype for Business Online, esse recurso requer Conferência PSTN da Microsoft, Exchange Unificação de Mensagens ou um provedor de audioconferência de terceiros.
  
 &#x2778; O cliente do Lync para Mac 2011 não pode exibir as apresentações do Microsoft Office 2013 PowerPoint quando elas foram compartilhadas em uma conferência pelo Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>Suporte a Voz (Telefonia)

<a name="BKMK_Telephony"> </a>

Esta tabela aborda recursos relacionados ao suporte a serviços de voz.
  
> [!NOTE]
> Skype for Business Os recursos de voz (Telefonia) estão limitados a determinados planos de assinatura Skype for Business Online. Para obter detalhes, consulte o [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).
  
| Recurso/funcionalidade | Skype for Business cliente 2015 ou 2016 | Skype for Business no Mac | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar uma chamada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Clique para chamar um contato  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir uma chamada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerencie o redirecionamento de chamada |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerenciamento de configurações de chamada em equipe |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Gerenciamento de delegados |&#x2714;|&#x2714;requer Skype for Business Server 2015 CU4 ou posterior |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Iniciação de uma chamada para um Grupo de Resposta |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Suporte aos serviços de emergência (E-911)  |&#x2714;|&#x2714;requer Skype for Business Server 2015 CU6 ou posterior |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notificação de IM para URI(s) SIP para chamada do E-911 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notificação de IM para lista de distribuição para chamada do E-911 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Conexão caixa postal, configurar ou alterar saudação |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notificação de chamada perdida |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Realização de chamadas em nome de outro contato (cenário gerente/delegado) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Administração de chamadas de terceiros quando configurado como delegado |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Gerencie volumes altos de chamadas |||||&#x2714;|&#x2714;||||
|Estacionamento de chamada  |&#x2714;||&#x2714; &#x2776; |||||||
|Atendimento de chamadas de grupo  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Roteamento com base no local  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gerenciar grupo de resposta/grupo de chamada de equipe |&#x2714;||&#x2714;|||||||
|Atender chamada de atendemento automático |&#x2714;||&#x2714;|||||||

&#x2776; Esse recurso não está disponível no Skype for Business Online.
  
## <a name="external-users-support"></a>Suporte a usuários externos

<a name="BKMK_ExternalUsers"> </a>

Esta tabela aborda recursos relacionados ao suporte para usuários externos que estão no PSTN.

|Recurso/funcionalidade | Skype for Business cliente 2015 ou 2016 | Skype for Business no Mac | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Iniciar o IM com um contato público  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Iniciar o IM com um contato federado |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Realizar chamadas de duas ou várias partes com usuários externos  <br/> (não disponível no Skype for Business Online) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>Gravação de suporte

<a name="BKMK_Recording"> </a>

Esta tabela aborda recursos relacionados ao suporte para gravação de reuniões.
  
| Futuro/recurso** | Skype for Business cliente 2015 ou 2016 | Skype for Business no Mac | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Gravação do lado do cliente de áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho e conteúdo carregado |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Registro no lado do cliente de transferências de arquivos, páginas OneNote compartilhadas e PowerPoint anotações |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Selecionar resolução de gravação preferencial |&#x2714;||&#x2714;|||||||

 &#x2776; Gravação não está disponível em determinados Skype for Business online autônomos. A gravação requer direitos Skype for Business cliente completos.
  
 &#x2777; Gravação de transferências de arquivo, páginas OneNote compartilhadas e PowerPoint anotações não está disponível no Skype for Business Online.
  
## <a name="modern-authentication"></a>Autenticação Moderna

<a name="BKMK_Recording"> </a>

Esta tabela aborda recursos que exigem suporte para autenticação moderna.
  
A autenticação moderna também requer uma topologia descrita [em Skype for Business topologias com suporte com Autenticação Moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).

| Recurso/funcionalidade | Skype for Business cliente 2015 ou 2016 | Skype for Business no Mac | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator para Mac 2011 | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticação Moderna |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticação multifafação  |&#x2714;|&#x2714;|&#x2714;|||||||
|Autenticação baseada em certificado  |&#x2714;(Somente dispositivo ingressado em domínio)| &#x2714;|&#x2714;(Somente dispositivo ingressado em domínio)  |||||||
|Autenticação Kerberos |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>Suporte a arquivamento, conformidade e registro em log

<a name="BKMK_Archiving"> </a>

Esta tabela aborda recursos relacionados ao suporte para funções de arquivamento e registro em log.

| Recurso/funcionalidade | Skype for Business cliente 2015 ou 2016 | Skype for Business no Mac | Cliente Lync 2013 | Aplicativo do Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator para Mac 2011** | Lync para Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Arquivamento de conversas de IM no Outlook Histórico de Conversas |&#x2714; &#x2776; |&#x2714;Se o histórico de conversas do lado do servidor estiver habilitado |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Salvo no Communicator para Mac |Salvo no Lync para Mac |
|Arquivamento do lado do cliente de áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho e conteúdo carregado |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Arquivamento do lado do cliente de transferências de arquivos, páginas OneNote compartilhadas e PowerPoint anotações  <br/> (indisponível Skype for Business Online)|&#x2714;||&#x2714;||&#x2714;|||||
|Acessar logs de entrada Skype for Business ícone na barra de tarefas |&#x2714;||&#x2714;|||||||

 &#x2776; Para usuários Skype for Business Online, esse recurso requer Exchange Online e é controlado pelo atributo Exchange caixa de correio In-Place Do usuário.
  
## <a name="client-limitations"></a>Limitações do cliente

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitações básicas de cliente

<a name="Full-Basic"> </a>

Os recursos a seguir estão disponíveis usando o cliente Completo e não estão disponíveis com o cliente Básico:

- Gerenciamento de configurações de chamada em equipe
- Gerenciamento de delegados
- Administração de chamadas de terceiros quando configurado como delegado
- Gerenciamento de um alto volume de chamadas
- Iniciação de uma chamada para um Grupo de Resposta
- Estacionamento de chamada
- Alterar saudação
- Atendimento de chamadas de grupo
- Emails de notificação de chamada perdida não são gerados quando um status do usuário está desabilitado e eles estão usando um cliente Outlook herdado (2013 ou anterior)

### <a name="online-or-hybrid-user-account-limitations"></a>Limitações de conta de usuário online ou híbrida

<a name="Online-Hybrid"> </a>

As contas de usuário podem existir online ou local e isso afetará os recursos disponíveis para esse usuário. Os usuários com contas Skype for Business Online não terão acesso aos seguintes recursos, mesmo com o cliente Completo:
  
- Presença aprimorada: use uma foto de qualquer site público para Minha Imagem
- Contatos: Pesquisar grupos de resposta
- Suporte a mensagens de mensagens im: integração de chat persistente (Chat de grupo)
- Suporte a mensagens de IM: escalone uma sala de Chat Persistente para uma reunião Skype for Business com um clique
- Usuários externos: realizar chamadas de duas ou várias partes com usuários externos

## <a name="see-also"></a>Confira também

<a name="Types"> </a>

[Planejar clientes e dispositivos](clients-and-devices.md)

[Atualizações mais recentes para versões Skype for Business que usam Windows Installer (MSI)](../../sfb-client-updates.md)