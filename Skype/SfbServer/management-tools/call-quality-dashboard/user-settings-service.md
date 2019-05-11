---
title: Serviço de configurações de usuário para o painel de controle de qualidade de chamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumo: Saiba mais sobre o serviço de configurações de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: ae87fcb28babbe3d9a480092d73e9c4cad2e1a76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914993"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="827a9-104">Serviço de configurações de usuário para o painel de controle de qualidade de chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="827a9-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="827a9-105">**Resumo:** Saiba mais sobre o serviço de configurações de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="827a9-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="827a9-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="827a9-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="827a9-107">O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="827a9-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="827a9-108">Serviço de configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="827a9-108">User Settings Service</span></span>

<span data-ttu-id="827a9-109">Configurações do usuário são pares de chave-valor que os aplicativos podem usar para armazenar metadados para várias finalidades, incluindo a personalização da base do aplicativo comportamentos por usuário.</span><span class="sxs-lookup"><span data-stu-id="827a9-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="827a9-110">Cada usuário recebe um armazenamento de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="827a9-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="827a9-111">Somente os proprietários podem adicionar, modificar e remover as configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="827a9-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="827a9-112">**Configurações globais**</span><span class="sxs-lookup"><span data-stu-id="827a9-112">**Global Settings**</span></span>
  
<span data-ttu-id="827a9-113">Configurações globais são as configurações de usuário pertencentes ao usuário do sistema e todos os usuários têm acesso somente leitura a eles.</span><span class="sxs-lookup"><span data-stu-id="827a9-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="827a9-114">Configurações globais são constantes: forem criados durante a criação do repositório, e elas nunca alteram.</span><span class="sxs-lookup"><span data-stu-id="827a9-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="827a9-115">Cada usuário pode substituir as configurações globais através da criação de configurações de usuário com as mesmas chaves.</span><span class="sxs-lookup"><span data-stu-id="827a9-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="827a9-116">Quando o aplicativo solicita as configurações de usuário efetivo, a API retorna um conjunto de configurações globais mescladas com as configurações de usuário, com cada configuração de usuário seja substituído a respectiva configuração global se chaves são iguais.</span><span class="sxs-lookup"><span data-stu-id="827a9-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="827a9-117">A API também pode retornar apenas as configurações do usuário para que os aplicativos podem descobrir quais configurações são substituídas.</span><span class="sxs-lookup"><span data-stu-id="827a9-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="827a9-118">As operações do REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="827a9-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="827a9-119">**Operação**</span><span class="sxs-lookup"><span data-stu-id="827a9-119">**Operation**</span></span>|<span data-ttu-id="827a9-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="827a9-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="827a9-121">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="827a9-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="827a9-122">Configurações de usuário Get retorna uma lista de configurações para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="827a9-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="827a9-123">Obter configuração de usuário</span><span class="sxs-lookup"><span data-stu-id="827a9-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="827a9-124">Obtenha a configuração do usuário retorna a configuração de um único usuário.</span><span class="sxs-lookup"><span data-stu-id="827a9-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

