---
title: Configurar um Serviço de Informações de Local secundário no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure um banco de dados de origem (SLS) de localização secundária para E9-1-1 em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 8f89afa61f235e05955d053e1a28b66a948d42fc
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500492"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a><span data-ttu-id="49eab-103">Configurar um Serviço de Informações de Local secundário no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="49eab-103">Configure a secondary Location Information service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="49eab-104">Configure um banco de dados de origem (SLS) de localização secundária para E9-1-1 em Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="49eab-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="49eab-105">Skype para Business Server fornece uma interface de serviço web que você pode usar para apontar o serviço de informações de local para um banco de dados de origem de localização secundário (SLS).</span><span class="sxs-lookup"><span data-stu-id="49eab-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="49eab-106">A interface de serviço da web que se conecta ao banco de dados SLS deve se adequar ao WSDL do serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="49eab-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="49eab-107">Se um banco de dados local e o banco de dados de localização secundária forem configurados, o serviço de informações de local primeiro consulta o banco de dados local e se nenhuma correspondência for encontrada, envia a solicitação de localização do cliente para o banco de dados SLS.</span><span class="sxs-lookup"><span data-stu-id="49eab-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="49eab-108">Se o local existe no SLS, o serviço de informações de local envia o local de volta para o cliente.</span><span class="sxs-lookup"><span data-stu-id="49eab-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="49eab-109">Para configurar o banco de dados de localização secundária</span><span class="sxs-lookup"><span data-stu-id="49eab-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="49eab-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="49eab-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="49eab-111">Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária.</span><span class="sxs-lookup"><span data-stu-id="49eab-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="49eab-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="49eab-112">See also</span></span>

[<span data-ttu-id="49eab-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="49eab-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)