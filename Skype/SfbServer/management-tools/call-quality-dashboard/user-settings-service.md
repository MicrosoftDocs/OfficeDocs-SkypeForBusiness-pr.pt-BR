---
title: Serviço de Configurações do Usuário para o Painel de Qualidade da Chamada (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumo: saiba mais sobre o Serviço de Configurações do Usuário, que faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803032"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="dd20b-104">Serviço de Configurações do Usuário para o Painel de Qualidade da Chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="dd20b-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="dd20b-105">**Resumo:** Saiba mais sobre o Serviço de Configurações do Usuário, que faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="dd20b-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="dd20b-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd20b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="dd20b-107">O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="dd20b-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="dd20b-108">Serviço de Configurações de Usuário</span><span class="sxs-lookup"><span data-stu-id="dd20b-108">User Settings Service</span></span>

<span data-ttu-id="dd20b-109">As configurações do usuário são pares chave-valor que os aplicativos podem usar para armazenar metadados para várias finalidades, incluindo personalização de comportamentos de aplicativos por usuário.</span><span class="sxs-lookup"><span data-stu-id="dd20b-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="dd20b-110">Cada usuário recebe um armazenamento para as configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="dd20b-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="dd20b-111">Somente os proprietários podem adicionar, modificar e remover configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="dd20b-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="dd20b-112">**Configurações Globais**</span><span class="sxs-lookup"><span data-stu-id="dd20b-112">**Global Settings**</span></span>
  
<span data-ttu-id="dd20b-113">As configurações globais são as configurações de usuário pertencentes ao usuário do sistema, e todos os usuários têm acesso somente leitura a eles.</span><span class="sxs-lookup"><span data-stu-id="dd20b-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="dd20b-114">As configurações globais são constantes: elas são criadas durante a criação do repositório e nunca mudam.</span><span class="sxs-lookup"><span data-stu-id="dd20b-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="dd20b-115">Cada usuário pode substituir as configurações globais criando configurações de usuário com as mesmas chaves.</span><span class="sxs-lookup"><span data-stu-id="dd20b-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="dd20b-116">Quando o aplicativo solicita as configurações efetivas do usuário, a API retorna um conjunto de configurações globais mescladas com as configurações do usuário, com cada configuração de usuário sobresondo a respectiva configuração global se as chaves são as mesmas.</span><span class="sxs-lookup"><span data-stu-id="dd20b-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="dd20b-117">A API também pode retornar apenas as configurações do usuário para que os aplicativos possam descobrir quais configurações foram substituídos.</span><span class="sxs-lookup"><span data-stu-id="dd20b-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="dd20b-118">As operações REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd20b-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="dd20b-119">**Operação**</span><span class="sxs-lookup"><span data-stu-id="dd20b-119">**Operation**</span></span>|<span data-ttu-id="dd20b-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dd20b-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="dd20b-121">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="dd20b-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="dd20b-122">Obter configurações de usuário retorna uma lista de configurações para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="dd20b-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="dd20b-123">Obter configuração de usuário</span><span class="sxs-lookup"><span data-stu-id="dd20b-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="dd20b-124">Obter Configuração do Usuário retorna uma configuração de usuário único.</span><span class="sxs-lookup"><span data-stu-id="dd20b-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

