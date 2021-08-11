---
title: Adicionar Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'O assistente Definir Novo Office Web Apps Server define um novo servidor Office Web Apps em sua implantação. Preencha com as seguintes informações:'
ms.openlocfilehash: 92dfe7d681453e432c7d1e3fb32377db32995641d5e7e47982db86af8185295a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302785"
---
# <a name="add-office-web-apps-server"></a>Adicionar Servidor do Office Web Apps

O **assistente Definir novo Office Web Apps Server** define um novo servidor Office Web Apps em sua implantação. Preencha com as seguintes informações:

 **Office Web Apps Server FQDN**: digite o nome de domínio totalmente qualificado do servidor que hospedará o servidor Office Web Apps

 **Office URL de** descoberta do Servidor de Aplicativos Web : Digite o URL (localizador de recursos uniforme) completo do servidor Office Web Apps

> [!TIP]
> O comportamento padrão da URL de descoberta do **Office Web Apps Server** é criar a URL com base no FQDN do servidor Office Web Apps no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Na maioria dos casos, não será necessário alterar o formato padrão. Talvez seja necessário alterar o formato padrão caso o servidor Office Web Apps e a URL de descoberta do servidor Office Web Apps sejam diferentes. Por exemplo, seu Office Web Apps Server é colocado na rede de perímetro e terá uma URL diferente com base no local.

 Office Web Apps Server é implantado em uma rede externa **(ou seja, perímetro/Internet)**: marque a caixa de seleção se o servidor do Office Web Apps for colocado fora do firewall interno, como a rede de perímetro, a rede externa ou outra zona de rede que não seja a mesma da sua rede interna.

## <a name="see-also"></a>Confira também

[Componentes e topologias para conferência](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)