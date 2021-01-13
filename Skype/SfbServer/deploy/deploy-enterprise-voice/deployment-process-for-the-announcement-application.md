---
title: Processo de implantação do aplicativo Comunicado no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo de implantação e etapas para o aplicativo Comunicado no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812301"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="6086d-103">Processo de implantação do aplicativo Comunicado no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6086d-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="6086d-104">Processo de implantação e etapas para o aplicativo Comunicado no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6086d-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6086d-105">O aplicativo Comunicado é um recurso do Enterprise Voice que permite configurar o que acontece com chamadas a ramais não atribuídos (extensões válidas para sua organização, mas que não estão atribuídas a uma pessoa ou telefone).</span><span class="sxs-lookup"><span data-stu-id="6086d-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="6086d-106">Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="6086d-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="6086d-107">O aplicativo Comunicado é instalado como um recurso do aplicativo Grupo de Resposta no servidor front-end ou servidor Standard Edition quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6086d-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="6086d-108">Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="6086d-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="6086d-109">Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo Comunicado.</span><span class="sxs-lookup"><span data-stu-id="6086d-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="6086d-110">Você deve implantar o Enterprise Voice antes de configurar os comunicados.</span><span class="sxs-lookup"><span data-stu-id="6086d-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="6086d-111">Os componentes exigidos pelo aplicativo Comunicado são instalados e habilitados quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6086d-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="6086d-112">**Processo de implantação do comunicado**</span><span class="sxs-lookup"><span data-stu-id="6086d-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="6086d-113">**Fase**</span><span class="sxs-lookup"><span data-stu-id="6086d-113">**Phase**</span></span>|<span data-ttu-id="6086d-114">**Etapas**</span><span class="sxs-lookup"><span data-stu-id="6086d-114">**Steps**</span></span>|<span data-ttu-id="6086d-115">**Funções**</span><span class="sxs-lookup"><span data-stu-id="6086d-115">**Roles**</span></span>|<span data-ttu-id="6086d-116">**Documentação de Implantação**</span><span class="sxs-lookup"><span data-stu-id="6086d-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6086d-117">Definir configurações do comunicado</span><span class="sxs-lookup"><span data-stu-id="6086d-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="6086d-118">Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS).</span><span class="sxs-lookup"><span data-stu-id="6086d-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="6086d-119">Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado.</span><span class="sxs-lookup"><span data-stu-id="6086d-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="6086d-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6086d-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="6086d-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="6086d-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="6086d-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6086d-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="6086d-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6086d-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="6086d-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="6086d-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="6086d-125">Criar ou excluir um comunicado no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6086d-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="6086d-126">Criar ou modificar um intervalo de números não atribuídos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6086d-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="6086d-127">Verifique a implantação do comunicado</span><span class="sxs-lookup"><span data-stu-id="6086d-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="6086d-128">Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.</span><span class="sxs-lookup"><span data-stu-id="6086d-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="6086d-129">(Opcional) Verificar a implantação do Comunicado no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6086d-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

