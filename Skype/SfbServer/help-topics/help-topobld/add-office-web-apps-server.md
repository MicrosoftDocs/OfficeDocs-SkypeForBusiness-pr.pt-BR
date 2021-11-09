---
title: Adicionar Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'O assistente Definir Novo Office Web Apps Server define um novo servidor Office Web Apps em sua implantação. Preencha com as seguintes informações:'
ms.openlocfilehash: 8a2565788879b86677784e26458cfba39d165076
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848764"
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