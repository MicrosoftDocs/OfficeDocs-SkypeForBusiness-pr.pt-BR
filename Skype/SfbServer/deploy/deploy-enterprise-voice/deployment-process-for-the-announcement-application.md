---
title: Processo de implantação para o aplicativo de anúncio no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo de implantação e etapas para o aplicativo de anúncio no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 5adaea25903968935cbaa00639546926781c004c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888068"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="cf6b5-103">Processo de implantação para o aplicativo de anúncio no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cf6b5-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="cf6b5-104">Processo de implantação e etapas para o aplicativo de anúncio no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cf6b5-105">O aplicativo de anúncio é um recurso de Enterprise Voice que permite que você configure o que acontece às chamadas para extensões não atribuídas (extensões que são válidos para a sua organização, mas não estão atribuídas a uma pessoa ou um telefone).</span><span class="sxs-lookup"><span data-stu-id="cf6b5-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="cf6b5-106">Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="cf6b5-107">O aplicativo de anúncio está instalado como um recurso do aplicativo do grupo de resposta no servidor Front-End ou Standard Edition servidor quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="cf6b5-108">Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="cf6b5-109">Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de anúncio.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="cf6b5-110">Você deve implantar o Enterprise Voice antes de configurar comunicados.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="cf6b5-111">Os componentes necessários para o aplicativo de anúncio estão instalados e ativados quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="cf6b5-112">**Processo de implantação do comunicado**</span><span class="sxs-lookup"><span data-stu-id="cf6b5-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="cf6b5-113">**Fase**</span><span class="sxs-lookup"><span data-stu-id="cf6b5-113">**Phase**</span></span>|<span data-ttu-id="cf6b5-114">**Etapas**</span><span class="sxs-lookup"><span data-stu-id="cf6b5-114">**Steps**</span></span>|<span data-ttu-id="cf6b5-115">**Funções**</span><span class="sxs-lookup"><span data-stu-id="cf6b5-115">**Roles**</span></span>|<span data-ttu-id="cf6b5-116">**Documentação de implantação**</span><span class="sxs-lookup"><span data-stu-id="cf6b5-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf6b5-117">Definir configurações do comunicado</span><span class="sxs-lookup"><span data-stu-id="cf6b5-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="cf6b5-118">Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS).</span><span class="sxs-lookup"><span data-stu-id="cf6b5-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="cf6b5-119">Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="cf6b5-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cf6b5-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="cf6b5-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="cf6b5-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="cf6b5-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="cf6b5-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="cf6b5-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cf6b5-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="cf6b5-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="cf6b5-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="cf6b5-125">Criar ou excluir um anúncio no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cf6b5-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="cf6b5-126">Criar ou modificar um intervalo de números não atribuído no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cf6b5-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="cf6b5-127">Verifique a implantação do comunicado</span><span class="sxs-lookup"><span data-stu-id="cf6b5-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="cf6b5-128">Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.</span><span class="sxs-lookup"><span data-stu-id="cf6b5-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="cf6b5-129">(Opcional) Verificar a implantação do comunicado na Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="cf6b5-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

