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
ms.openlocfilehash: df8f2ba98215a597e9532e636b022edf9cb1ec19
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="add-office-web-apps-server"></a>Adicionar Servidor do Office Web Apps
 
O assistente **Definir novo Office Web Apps Server** define um novo Office Web Apps Server em sua implantação. Preencha as seguintes informações:
  
 **FQDN do servidor do Office Web Apps**: digite o nome de domínio totalmente qualificado do servidor que hospedará o Office Web Apps Server
  
 **URL de descoberta do Office Web Apps Server**: digite o localizador de recursos uniforme completo (URL) do servidor Office Web Apps
  
> [!TIP]
> O comportamento padrão da **URL de descoberta do Office Web Apps Server** é criar a URL com base no FQDN do Office Web Apps Server, no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Na maioria dos casos, não será preciso alterar o formato padrão. Você pode precisar alterar o formato padrão que o Office Web Apps Server e a URL de descoberta do Office Web Apps Server devem ser diferente. Por exemplo, o Office Web Apps Server é colocado na rede de perímetro e terá uma URL diferente, com base no local.
  
 **Office Web Apps Server é implantado em uma rede externa (ou seja, de perímetro/Internet)**: marque a caixa de seleção se o Office Web Apps Server é colocado fora do firewall interno, como a rede de perímetro, rede externa ou outra zona de rede que não é o mesmo que sua rede interna.
  
## <a name="see-also"></a>Consulte também

#### 

[Componentes e topologias para conferência](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)

