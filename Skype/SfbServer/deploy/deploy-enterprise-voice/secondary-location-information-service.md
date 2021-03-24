---
title: Configurar um serviço secundário de Informações de Localização no Skype for Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure um banco de dados SLS (fonte de localização secundária) para E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 7a81d8573ca0425d4d445dc00f257f014a39d8c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103377"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="7037d-103">Configurar um serviço secundário de Informações de Localização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7037d-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="7037d-104">Configure um banco de dados SLS (fonte de localização secundária) para E9-1-1 no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7037d-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="7037d-105">O Skype for Business Server fornece uma interface de serviço Web que você pode usar para apontar o serviço de Informações de Localização para um banco de dados SLS (Secondary Location Source).</span><span class="sxs-lookup"><span data-stu-id="7037d-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="7037d-106">A interface do serviço Web que se conecta ao banco de dados SLS deve estar em conformidade com o WSDL do serviço de Informações de Local.</span><span class="sxs-lookup"><span data-stu-id="7037d-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="7037d-107">Se um banco de dados de localização e um banco de dados de localização secundário estão configurados, o serviço de Informações de Local primeiro consulta o banco de dados de localização e, se nenhuma combinação for encontrada, enviará a solicitação de local do cliente para o banco de dados SLS.</span><span class="sxs-lookup"><span data-stu-id="7037d-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="7037d-108">Se o local existir no SLS, o serviço Informações de Local enviará o local de volta para o cliente.</span><span class="sxs-lookup"><span data-stu-id="7037d-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="7037d-109">Para configurar um banco de dados de Local Secundário</span><span class="sxs-lookup"><span data-stu-id="7037d-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="7037d-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="7037d-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7037d-111">Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária.</span><span class="sxs-lookup"><span data-stu-id="7037d-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="7037d-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="7037d-112">See also</span></span>

[<span data-ttu-id="7037d-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7037d-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)