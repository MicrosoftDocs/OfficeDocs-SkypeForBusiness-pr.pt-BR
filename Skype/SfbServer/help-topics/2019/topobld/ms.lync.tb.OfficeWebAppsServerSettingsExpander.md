---
title: Editar Configurações do Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Edite as propriedades do servidor web Office Web Apps configurado. As propriedades a seguir estão disponíveis para edição:'
ms.openlocfilehash: 75a9822fb91e145eb28d8df506eaa392663e1fd1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769239"
---
# <a name="edit-office-web-apps-server-settings"></a>Editar Configurações do Servidor do Office Web Apps

Edite as propriedades do servidor web Office Web Apps configurado. As propriedades a seguir estão disponíveis para edição:

 **Office Web Apps Server FQDN**: Essa propriedade define o nome de domínio totalmente qualificado do servidor Office Web Apps e deve corresponder a um registro de host A ou AAAA do sistema de nomes de domínio (DNS) (se IPv6 estiver sendo usado).

 **Office URL** de descoberta do Servidor web apps : o url (localizador de recursos uniforme) para acesso do cliente ao servidor Office Web Apps, talvez seja necessário editar esse endereço de seu padrão se o servidor for colocado em outra zona de rede diferente da rede interna da sua implantação.

Marque a caixa de seleção **Office Web Apps Server é implantado em uma rede externa** se esse servidor for implantado em sua rede de perímetro ou em outra zona de rede que esteja fora de seu firewall interno, separando a rede de perímetro, redes menos confiáveis e a Internet de sua implantação interna.

![Office Web Apps Configurações Expander.](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Confira também

[Componentes e topologias para conferência](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)