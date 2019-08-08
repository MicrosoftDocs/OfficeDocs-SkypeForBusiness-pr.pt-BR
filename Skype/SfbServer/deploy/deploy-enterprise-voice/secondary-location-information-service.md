---
title: Configurar um serviço de informações de localização secundário no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurar um banco de dados de endereço de local secundário (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240162"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="d9fd8-103">Configurar um serviço de informações de localização secundário no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d9fd8-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="d9fd8-104">Configurar um banco de dados de endereço de local secundário (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d9fd8-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d9fd8-105">O Skype for Business Server oferece uma interface de serviço Web que você pode usar para apontar o serviço de informações de localização para um banco de dados de local secundário (SLS).</span><span class="sxs-lookup"><span data-stu-id="d9fd8-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="d9fd8-106">A interface do serviço Web que se conecta ao banco de dados SLS deve estar de acordo com o WSDL do serviço de informações de localização.</span><span class="sxs-lookup"><span data-stu-id="d9fd8-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="d9fd8-107">Se o banco de dados de localização e o banco de dados de local secundário estiverem configurados, o serviço informações de localização primeiro consultará o banco de dados de localização e, se nenhuma correspondência for encontrada, envia a solicitação de localização do cliente para o banco de dados SLS.</span><span class="sxs-lookup"><span data-stu-id="d9fd8-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="d9fd8-108">Se o local existir no SLS, o serviço de informações de localização enviará o local de volta ao cliente.</span><span class="sxs-lookup"><span data-stu-id="d9fd8-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="d9fd8-109">Para configurar o banco de dados de localização secundária</span><span class="sxs-lookup"><span data-stu-id="d9fd8-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="d9fd8-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="d9fd8-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d9fd8-111">Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária.</span><span class="sxs-lookup"><span data-stu-id="d9fd8-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="d9fd8-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="d9fd8-112">See also</span></span>

[<span data-ttu-id="d9fd8-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="d9fd8-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

