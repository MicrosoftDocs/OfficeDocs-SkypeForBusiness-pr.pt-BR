---
title: Editar Configurações do Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Edite as propriedades do Servidor do Office Web Apps configurado. As propriedades a seguir estão disponíveis para edição:'
ms.openlocfilehash: 0c5dbff11d6cc2f6b25f3afa77cfe12e1e511a8a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121074"
---
# <a name="edit-office-web-apps-server-settings"></a>Editar Configurações do Servidor do Office Web Apps

Edite as propriedades do Servidor do Office Web Apps configurado. As propriedades a seguir estão disponíveis para edição:

 **FQDN** do Servidor do Office Web Apps : Essa propriedade define o nome de domínio totalmente qualificado do Servidor do Office Web Apps e deve corresponder a um registro de host A ou AAAA do sistema de nomes de domínio (DNS) (se IPv6 estiver sendo usado).

 **URL** de descoberta do Servidor do Office Web Apps : O url (localizador de recursos uniforme) para acesso do cliente ao Servidor do Office Web Apps, talvez seja necessário editar esse endereço de seu padrão se o servidor for colocado em outra zona de rede diferente da rede interna da sua implantação.

Marque a caixa de seleção **Office Web Apps Server é implantado em uma rede externa** se esse servidor for implantado em sua rede de perímetro ou em outra zona de rede que esteja fora de seu firewall interno, separando a rede de perímetro, redes menos confiáveis e a Internet de sua implantação interna.

![Expansador de Configurações do Office Web Apps](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Confira também

[Componentes e topologias para conferência](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)