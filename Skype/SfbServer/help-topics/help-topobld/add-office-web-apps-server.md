---
title: Adicionar Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'O assistente Definir Novo Servidor do Office Web Apps define um novo Servidor do Office Web Apps em sua implantação. Preencha com as seguintes informações:'
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828591"
---
# <a name="add-office-web-apps-server"></a>Adicionar Servidor do Office Web Apps

O **assistente Definir Novo Servidor do Office Web Apps** define um novo Servidor do Office Web Apps em sua implantação. Preencha com as seguintes informações:

 **FQDN do Servidor** do Office Web Apps: digite o nome de domínio totalmente qualificado do servidor que hospedará o Servidor do Office Web Apps

 **URL de descoberta do Servidor do Office Web Apps:** digite a URL completa do Servidor do Office Web Apps

> [!TIP]
> O comportamento padrão da URL de descoberta do Servidor do **Office Web Apps** é criar a URL com base no FQDN do Servidor do Office Web Apps no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Na maioria dos casos, não será necessário alterar o formato padrão. Talvez seja necessário alterar o formato padrão caso o Servidor do Office Web Apps e a URL de descoberta do Servidor do Office Web Apps sejam diferentes. Por exemplo, seu Servidor do Office Web Apps é colocado na rede de perímetro e terá uma URL diferente com base no local.

 O Servidor do Office Web Apps é implantado em uma rede externa **(ou seja, de perímetro/Internet)**: marque a caixa de seleção se o Servidor do Office Web Apps for colocado fora do firewall interno, como a rede de perímetro, a rede externa ou outra zona de rede que não seja a mesma da rede interna.

## <a name="see-also"></a>Confira também

[Componentes e topologias para conferência](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
