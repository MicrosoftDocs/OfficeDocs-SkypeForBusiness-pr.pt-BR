---
title: Configurar um aplicativo SNMP no Skype for Business Server 2015
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configure um aplicativo SNMP para funcionar com o E9-1-1 em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 6024119042bede23f6b38f07c6ccdffa86a76db7
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500414"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a><span data-ttu-id="648ac-103">Configurar um aplicativo SNMP no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="648ac-103">Configure an SNMP application in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="648ac-104">Configure um aplicativo SNMP para funcionar com o E9-1-1 em Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="648ac-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="648ac-105">Skype para Business Server inclui uma interface de serviço da web padrão que você pode usar para conectar-se o serviço de informações de local aos aplicativos de protocolo de gerenciamento de rede simples (SNMP) que correspondem endereços MAC com porta e trocar informações.</span><span class="sxs-lookup"><span data-stu-id="648ac-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="648ac-106">Se um aplicativo SNMP é instalado e o serviço de informações de local não conseguir localizar uma correspondência no banco de dados local, o serviço de informações de local de consulta automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="648ac-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="648ac-107">O serviço de informações de local, em seguida, usa as informações de porta e opção retornadas pelo aplicativo SNMP para consultar novamente o banco de dados local.</span><span class="sxs-lookup"><span data-stu-id="648ac-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="648ac-108">Endereços MAC não estão disponíveis em computadores que executam o Windows 8.</span><span class="sxs-lookup"><span data-stu-id="648ac-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="648ac-109">Para configurar a URL do aplicativo SNMP</span><span class="sxs-lookup"><span data-stu-id="648ac-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="648ac-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="648ac-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="648ac-111">Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP.</span><span class="sxs-lookup"><span data-stu-id="648ac-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="648ac-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="648ac-112">See also</span></span>

[<span data-ttu-id="648ac-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="648ac-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

