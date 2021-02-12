---
title: Expansor de Configurações Gerais de Aplicativo Externo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.
ms.openlocfilehash: 55f6bfee68370f8f341080e54953120e48f628f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804761"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="757a5-103">Expansor de Configurações Gerais de Aplicativo Externo</span><span class="sxs-lookup"><span data-stu-id="757a5-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="757a5-104">Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.</span><span class="sxs-lookup"><span data-stu-id="757a5-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="757a5-105">Existem duas seções que você pode modificar:</span><span class="sxs-lookup"><span data-stu-id="757a5-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="757a5-106">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="757a5-106">General settings</span></span>
> 
> <span data-ttu-id="757a5-107">Configurações de próximo salto</span><span class="sxs-lookup"><span data-stu-id="757a5-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="757a5-108">Configurações Gerais</span><span class="sxs-lookup"><span data-stu-id="757a5-108">General Settings</span></span>

<span data-ttu-id="757a5-p101">Você pode modificar o FQDN (nome de domínio totalmente qualificado) para o pool de servidor de aplicativos confiáveis. Edite o nome do pool FQDN. Os registros de host (A) DNS (Domain Name System) devem existir antes que clientes ou servidores possam se conectar ao novo nome de pool.</span><span class="sxs-lookup"><span data-stu-id="757a5-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="757a5-p102">Selecione  **Habilite a replicação dos dados de configuração para este pool** caso você necessite da replicação dos dados de configuração para este pool. Limpe a marca de seleção caso não queira replicar os dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="757a5-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="757a5-114">Configurações de Próximo Salto</span><span class="sxs-lookup"><span data-stu-id="757a5-114">Next Hop Settings</span></span>

<span data-ttu-id="757a5-115">Você pode especificar o servidor do próximo salto do pool de servidores de aplicativos confiáveis selecionando o pool de Front-End Enterprise Edition definido ou o Servidor de Front End Standard Edition na lista lista drop-down.</span><span class="sxs-lookup"><span data-stu-id="757a5-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="757a5-116">Um Diretor ou pool de Diretores não é uma escolha válida para um próximo salto de servidor de aplicativos confiáveis e não aparecerão na lista.</span><span class="sxs-lookup"><span data-stu-id="757a5-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="757a5-117">Clique **em OK** para aceitar e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="757a5-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="757a5-118">Clique em  **Cancelar** para descartar suas alterações e sair da página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="757a5-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

