---
title: Adicionar Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'O assistente definir novo Office Web Apps Server define um novo servidor do Office Web Apps na sua implantação. Preencha as seguintes informações:'
ms.openlocfilehash: 9ca5be070d4a79a2cb011a1e91bd0613f21e8700
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798448"
---
# <a name="add-office-web-apps-server"></a>Adicionar Servidor do Office Web Apps

O assistente **definir novo Office Web Apps Server** define um novo servidor do Office Web Apps na sua implantação. Preencha as seguintes informações:

 **Office Web Apps Server FQDN**: digite o nome de domínio totalmente qualificado do servidor que hospedará o servidor do Office Web Apps

 **URL de descoberta do servidor do Office Web Apps**: digite a URL (Uniform Resource Locator) completa do servidor do Office Web Apps

> [!TIP]
> O comportamento padrão da **URL de descoberta do Office Web Apps Server** é criar a URL com base no FQDN do servidor do Office Web Apps no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Na maioria dos casos, não será preciso alterar o formato padrão. Talvez seja necessário alterar o formato padrão no caso de o servidor do Office Web Apps e da URL de descoberta do Office Web Apps Server devem ser diferentes. Por exemplo, seu servidor do Office Web Apps é colocado na rede de perímetro e terá uma URL diferente com base no local.

 O **Office Web Apps Server é implantado em uma rede externa (ou seja, perímetro/Internet)**: marque a caixa de seleção se o servidor do Office Web Apps estiver fora do seu firewall interno, como a rede de perímetro, a rede externa ou outra zona de rede que não seja igual à sua rede interna.

## <a name="see-also"></a>Confira também

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
