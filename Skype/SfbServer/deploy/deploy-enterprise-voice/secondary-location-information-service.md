---
title: Configurar um serviço de Informações de Local secundário no Skype for Business Server
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
description: Configure um banco de dados de Origem de Local Secundária (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830641"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="854c1-103">Configurar um serviço de Informações de Local secundário no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="854c1-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="854c1-104">Configure um banco de dados de Origem de Local Secundária (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="854c1-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="854c1-105">O Skype for Business Server fornece uma interface de serviço Web que você pode usar para apontar o serviço informações de local para um banco de dados de Origem de Local Secundário (SLS).</span><span class="sxs-lookup"><span data-stu-id="854c1-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="854c1-106">A interface do serviço Web que se conecta ao banco de dados SLS deve estar em conformidade com o WSDL do serviço de Informações de Local.</span><span class="sxs-lookup"><span data-stu-id="854c1-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="854c1-107">Se um banco de dados de localização e um banco de dados de localização secundário estão configurados, o serviço de Informações de Local primeiro consulta o banco de dados de localização e, se nenhuma combinação for encontrada, envia a solicitação de local do cliente para o banco de dados SLS.</span><span class="sxs-lookup"><span data-stu-id="854c1-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="854c1-108">Se o local existir no SLS, o serviço de Informações de Local enviará o local de volta para o cliente.</span><span class="sxs-lookup"><span data-stu-id="854c1-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="854c1-109">Para configurar um banco de dados de Localização Secundária</span><span class="sxs-lookup"><span data-stu-id="854c1-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="854c1-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="854c1-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="854c1-111">Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária.</span><span class="sxs-lookup"><span data-stu-id="854c1-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="854c1-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="854c1-112">See also</span></span>

[<span data-ttu-id="854c1-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="854c1-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

