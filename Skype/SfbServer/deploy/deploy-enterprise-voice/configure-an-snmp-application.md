---
title: Configurar um aplicativo SNMP no Skype for Business Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configure um aplicativo SNMP para funcionar com o E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804151"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="cb0a7-103">Configurar um aplicativo SNMP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cb0a7-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="cb0a7-104">Configure um aplicativo SNMP para funcionar com o E9-1-1 no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cb0a7-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="cb0a7-105">O Skype for Business Server inclui uma interface de serviço Web padrão que você pode usar para conectar o serviço de Informações de Local a aplicativos SNMP (Simple Network Management Protocol) que combinam endereços MAC com informações de porta e de comutamento.</span><span class="sxs-lookup"><span data-stu-id="cb0a7-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="cb0a7-106">Se um aplicativo SNMP estiver instalado e o serviço de Informações de Local não encontrar uma combinação no banco de dados de localização, o serviço de Informações de Local consultará automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="cb0a7-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="cb0a7-107">Em seguida, o serviço de Informações de Local usa as informações de porta e de comutadores retornadas pelo aplicativo SNMP para consultar o banco de dados de localização novamente.</span><span class="sxs-lookup"><span data-stu-id="cb0a7-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb0a7-108">Os endereços MAC não estão disponíveis em computadores que executam o Windows 8.</span><span class="sxs-lookup"><span data-stu-id="cb0a7-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="cb0a7-109">Para configurar a URL do aplicativo SNMP</span><span class="sxs-lookup"><span data-stu-id="cb0a7-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="cb0a7-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="cb0a7-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="cb0a7-111">Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP.</span><span class="sxs-lookup"><span data-stu-id="cb0a7-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="cb0a7-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="cb0a7-112">See also</span></span>

[<span data-ttu-id="cb0a7-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb0a7-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

