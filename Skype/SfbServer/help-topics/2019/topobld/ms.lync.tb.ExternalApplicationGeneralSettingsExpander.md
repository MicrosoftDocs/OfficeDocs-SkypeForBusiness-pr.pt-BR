---
title: Expansor de Configurações Gerais de Aplicativo Externo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.
ms.openlocfilehash: eacc0c854290fcf24196a8e4c58829231dc725c4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793739"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="f00cd-103">Expansor de Configurações Gerais de Aplicativo Externo</span><span class="sxs-lookup"><span data-stu-id="f00cd-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="f00cd-104">Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.</span><span class="sxs-lookup"><span data-stu-id="f00cd-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="f00cd-105">Há duas seções que você pode modificar:</span><span class="sxs-lookup"><span data-stu-id="f00cd-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="f00cd-106">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="f00cd-106">General settings</span></span>
> 
> <span data-ttu-id="f00cd-107">Configurações de próximo salto</span><span class="sxs-lookup"><span data-stu-id="f00cd-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="f00cd-108">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="f00cd-108">General Settings</span></span>

<span data-ttu-id="f00cd-109">Você pode modificar o nome de domínio totalmente qualificado (FQDN) atual para o pool do servidor de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="f00cd-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="f00cd-110">Edite o nome do FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="f00cd-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="f00cd-111">Os registros de host (A) do sistema de nome de domínio (DNS) devem existir para a nova entrada antes que os clientes ou servidores possam se conectar ao novo nome do pool.</span><span class="sxs-lookup"><span data-stu-id="f00cd-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="f00cd-112">Selecione **habilitar a replicação de dados de configuração para esse pool** se você precisar ter a replicação de dados de configuração para esse pool.</span><span class="sxs-lookup"><span data-stu-id="f00cd-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="f00cd-113">Desmarque a caixa de seleção se você não quiser replicar os dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="f00cd-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="f00cd-114">Próximas configurações de salto</span><span class="sxs-lookup"><span data-stu-id="f00cd-114">Next Hop Settings</span></span>

<span data-ttu-id="f00cd-115">Você pode especificar o próximo servidor de salto do pool de servidores de aplicativos confiáveis selecionando o pool de front-end do Enterprise Edition definido ou o servidor front-end da edição Standard na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f00cd-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="f00cd-116">Um diretor ou um pool de diretor não é uma seleção válida para um próximo salto do servidor de aplicativos confiável e não aparecerá na lista.</span><span class="sxs-lookup"><span data-stu-id="f00cd-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="f00cd-117">Clique em **OK** para aceitar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="f00cd-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="f00cd-118">Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="f00cd-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

