---
title: Serviço de configurações do usuário para o painel de qualidade de chamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumo: Saiba mais sobre o serviço configurações do usuário, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816640"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="b976b-104">Serviço de configurações do usuário para o painel de qualidade de chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="b976b-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="b976b-105">**Resumo:** Saiba mais sobre o serviço configurações do usuário, que faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="b976b-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b976b-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b976b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b976b-107">O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="b976b-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="b976b-108">Serviço de configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="b976b-108">User Settings Service</span></span>

<span data-ttu-id="b976b-109">As configurações de usuário são pares de valor chave que os aplicativos podem usar para armazenar metadados para várias finalidades, incluindo a personalização de comportamentos do aplicativo por usuário.</span><span class="sxs-lookup"><span data-stu-id="b976b-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="b976b-110">Cada usuário recebe um armazenamento de configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="b976b-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="b976b-111">Somente os proprietários podem adicionar, modificar e remover as configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="b976b-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="b976b-112">**Configurações globais**</span><span class="sxs-lookup"><span data-stu-id="b976b-112">**Global Settings**</span></span>
  
<span data-ttu-id="b976b-113">As configurações globais são as configurações de usuário pertencentes ao usuário do sistema e todos os usuários têm acesso somente leitura a elas.</span><span class="sxs-lookup"><span data-stu-id="b976b-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="b976b-114">As configurações globais são constantes: elas são criadas durante a criação do repositório e nunca mudam.</span><span class="sxs-lookup"><span data-stu-id="b976b-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="b976b-115">Cada usuário pode substituir as configurações globais criando configurações de usuário com as mesmas chaves.</span><span class="sxs-lookup"><span data-stu-id="b976b-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="b976b-116">Quando o aplicativo solicita as configurações de usuário efetivas, a API retorna um conjunto de configurações globais mescladas com as configurações de usuário, com cada configuração de usuário substituindo a respectiva configuração global se as chaves forem iguais.</span><span class="sxs-lookup"><span data-stu-id="b976b-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="b976b-117">A API também pode retornar apenas as configurações do usuário para que os aplicativos possam descobrir quais configurações são substituídas.</span><span class="sxs-lookup"><span data-stu-id="b976b-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="b976b-118">As operações REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b976b-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="b976b-119">**Operação**</span><span class="sxs-lookup"><span data-stu-id="b976b-119">**Operation**</span></span>|<span data-ttu-id="b976b-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b976b-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b976b-121">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="b976b-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="b976b-122">Obter configurações do usuário retorna uma lista de configurações para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="b976b-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="b976b-123">Obter configuração de usuário</span><span class="sxs-lookup"><span data-stu-id="b976b-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="b976b-124">Obter configuração de usuário retorna uma única configuração de usuário.</span><span class="sxs-lookup"><span data-stu-id="b976b-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

