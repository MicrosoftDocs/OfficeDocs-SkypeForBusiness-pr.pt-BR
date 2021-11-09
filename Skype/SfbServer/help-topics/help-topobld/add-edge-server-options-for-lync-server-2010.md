---
title: Adicionar Opções de Servidor de Borda para o Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Você define um novo pool de Borda ou Servidor de Borda e tem a oportunidade de definir recursos para o novo servidor ou pool. As opções possíveis são:'
ms.openlocfilehash: 0c02e03a1e0e1a8c8455be48915f1c488f4d021f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845534"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Adicionar Opções de Servidor de Borda para o Lync Server 2010

Você define um novo pool de Borda ou Servidor de Borda e tem a oportunidade de definir recursos para o novo servidor ou pool. As opções possíveis são:

- **Usar um único FQDN e endereço IP**: marque a caixa de seleção para usar um único endereço IPv4 ou IPv6 (se você escolher usar IPv4 e IPv6, será necessário definir um de cada tipo de endereço IP) e nome de domínio totalmente qualificado (FQDN) para as interfaces de Borda externas.

    > [!IMPORTANT]
    > Se você escolher essa opção, usará somente um endereço IP ou um IPv4 e um IPv6, mas deverá atribuir números de porta diferentes a cada interface de Borda.

- **Habilitar federação (porta 5061)**: marque essa caixa de seleção se for federar com outras federações SIP, provedores ou ofertas hospedadas que usam o protocolo de início de sessão (SIP).

- O endereço IP externo deste pool de Borda é convertido por **NAT**: marque essa caixa de seleção se você usar endereços IP privados para as interfaces externas de Borda e fornecerá um dispositivo NAT (conversão de endereço de rede) para colocar o Servidor de Borda ou pool de Borda logicamente para trás.

## <a name="see-also"></a>Confira também

[Planejando o acesso de usuários externos](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[Implantação de acesso de usuários externos](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)