---
title: Adicionar Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'O assistente definir novo servidor do Office Web Apps define um novo servidor do Office Web Apps em sua implantação. Preencha com as seguintes informações:'
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218722"
---
# <a name="add-office-web-apps-server"></a>Adicionar Servidor do Office Web Apps

O assistente **definir novo servidor do Office Web Apps** define um novo servidor do Office Web Apps em sua implantação. Preencha com as seguintes informações:

 **FQDN do servidor do Office Web Apps**: digite o nome de domínio totalmente qualificado do servidor que hospedará o servidor do Office Web Apps

 **URL de descoberta do Office Web Apps Server**: digite o Uniform Resource Locator (URL) completo do servidor do Office Web Apps

> [!TIP]
> O comportamento padrão da **URL de descoberta do Office Web Apps Server** é criar a URL com base no FQDN do servidor do Office Web Apps no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Na maioria dos casos, não será necessário alterar o formato padrão. Talvez seja necessário alterar o formato padrão caso o servidor do Office Web Apps e a URL de descoberta do Office Web Apps Server sejam diferentes. Por exemplo, seu servidor do Office Web Apps é colocado na rede de perímetro e terá uma URL diferente com base no local.

 O **servidor do Office Web Apps é implantado em uma rede externa (ou seja, perímetro/Internet)**: marque a caixa de seleção se o servidor do Office Web Apps for colocado fora do firewall interno, como a rede de perímetro, a rede externa ou outra zona de rede que não seja a mesma que a sua rede interna.

## <a name="see-also"></a>Confira também

[Componentes e topologias para conferência](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
