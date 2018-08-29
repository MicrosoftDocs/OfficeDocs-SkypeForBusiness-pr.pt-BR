---
title: Adicionar Servidor do Office Web Apps
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'O assistente definir novo Office Web Apps Server define um novo Office Web Apps Server em sua implantação. Preencha as seguintes informações:'
ms.openlocfilehash: 34f8f1b58cc6d937432b667a110eb805dd5a2c88
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245765"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="6b7db-104">Adicionar Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="6b7db-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="6b7db-105">O assistente **Definir novo Office Web Apps Server** define um novo Office Web Apps Server em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="6b7db-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="6b7db-106">Preencha as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6b7db-106">You fill in the following information:</span></span>

 <span data-ttu-id="6b7db-107">**FQDN do servidor do Office Web Apps**: digite o nome de domínio totalmente qualificado do servidor que hospedará o Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="6b7db-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="6b7db-108">**URL de descoberta do Office Web Apps Server**: digite o localizador de recursos uniforme completo (URL) do servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="6b7db-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="6b7db-109">O comportamento padrão da **URL de descoberta do Office Web Apps Server** é criar a URL com base no FQDN do Office Web Apps Server, no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="6b7db-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="6b7db-110">Na maioria dos casos, não será preciso alterar o formato padrão.</span><span class="sxs-lookup"><span data-stu-id="6b7db-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="6b7db-111">Você pode precisar alterar o formato padrão que o Office Web Apps Server e a URL de descoberta do Office Web Apps Server devem ser diferente.</span><span class="sxs-lookup"><span data-stu-id="6b7db-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="6b7db-112">Por exemplo, o Office Web Apps Server é colocado na rede de perímetro e terá uma URL diferente, com base no local.</span><span class="sxs-lookup"><span data-stu-id="6b7db-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="6b7db-113">**Office Web Apps Server é implantado em uma rede externa (ou seja, de perímetro/Internet)**: marque a caixa de seleção se o Office Web Apps Server é colocado fora do firewall interno, como a rede de perímetro, rede externa ou outra zona de rede que não é o mesmo que sua rede interna.</span><span class="sxs-lookup"><span data-stu-id="6b7db-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b7db-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6b7db-114">See also</span></span>

[<span data-ttu-id="6b7db-115">Componentes e topologias para conferência</span><span class="sxs-lookup"><span data-stu-id="6b7db-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)