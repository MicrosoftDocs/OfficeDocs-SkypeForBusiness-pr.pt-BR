---
title: Expansor de configurações gerais de aplicativo externo
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um servidor de aplicativos confiáveis que já foi definido, siga estas instruções.
ms.openlocfilehash: 73010b40bd5c06c1e59d9b2fee0e4fde3d247732
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374543"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="542b7-103">Expansor de configurações gerais de aplicativo externo</span><span class="sxs-lookup"><span data-stu-id="542b7-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="542b7-104">Para editar as propriedades de um servidor de aplicativos confiáveis que já foi definido, siga estas instruções.</span><span class="sxs-lookup"><span data-stu-id="542b7-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="542b7-105">Há duas seções que você pode modificar:</span><span class="sxs-lookup"><span data-stu-id="542b7-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="542b7-106">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="542b7-106">General settings</span></span>
> 
> <span data-ttu-id="542b7-107">Configurações de próximo salto</span><span class="sxs-lookup"><span data-stu-id="542b7-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="542b7-108">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="542b7-108">General Settings</span></span>

<span data-ttu-id="542b7-109">Você pode modificar o nome de domínio totalmente qualificado (FQDN) atual para o pool de servidores de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="542b7-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="542b7-110">Edite o nome do FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="542b7-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="542b7-111">Os registros de host (A) do sistema de nome de domínio (DNS) devem existir para a nova entrada antes de clientes ou servidores podem se conectar para o novo nome do pool.</span><span class="sxs-lookup"><span data-stu-id="542b7-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="542b7-112">Selecione **habilitar replicação de dados de configuração para este pool** se você precisa ter a replicação de dados de configuração para este pool.</span><span class="sxs-lookup"><span data-stu-id="542b7-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="542b7-113">Desmarque a marca de seleção se não desejar replicar os dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="542b7-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="542b7-114">Configurações de próximo salto</span><span class="sxs-lookup"><span data-stu-id="542b7-114">Next Hop Settings</span></span>

<span data-ttu-id="542b7-115">Você pode especificar o servidor de próximo salto do pool de servidores de aplicativos confiáveis, selecionando o pool de Front End do Enterprise Edition ou Standard Edition servidor Front-End de definido na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="542b7-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="542b7-116">Um diretor ou diretor pool não é uma seleção válida para um próximo salto do servidor aplicativos confiáveis e não aparecerão na lista.</span><span class="sxs-lookup"><span data-stu-id="542b7-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="542b7-117">Clique em **Okey** para aceitar e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="542b7-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="542b7-118">Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="542b7-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

