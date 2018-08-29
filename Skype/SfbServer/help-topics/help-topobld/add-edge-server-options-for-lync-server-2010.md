---
title: Adicionar opções de servidor de borda do Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Você pode define um novo servidor de borda ou pool de borda e é apresentados a oportunidade de definir os recursos para o novo servidor ou pool. As opções que você pode escolher são:'
ms.openlocfilehash: d42a7cf7c926e8a879a148c3e4dcb7cc7624d23e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23257343"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Adicionar opções de servidor de borda do Lync Server 2010

Você pode define um novo servidor de borda ou pool de borda e é apresentados a oportunidade de definir os recursos para o novo servidor ou pool. As opções que você pode escolher são:

- **Use um único endereço IP e FQDN**: marque a caixa de seleção usar um único IPv4 ou IPv6 (se você optar por usar o IPv4 e IPv6, e em seguida, você precisará defini-la de cada tipo de endereço IP) endereço e o nome domínio totalmente qualificado (FQDN) do External interfaces de borda.

    > [!IMPORTANT]
    > Se você escolher essa opção, você usará somente um endereço IP, ou um IPv4 e um IPv6, mas você deve atribuir números de porta diferentes para cada interface de borda.

- **Habilitar federação (porta 5061)**: marque essa caixa de seleção se for federar com outras federações SIP, provedores ou ofertas hospedadas que usam o protocolo de iniciação de sessão (SIP).

- **O endereço IP externo deste pool de borda é convertido por NAT**: marque essa caixa de seleção se você usar endereços IP privados das interfaces externas de borda e fornecerá um dispositivo NAT (conversão) de endereço de rede para colocar o servidor de borda ou pool de borda logicamente atrás.

## <a name="see-also"></a>Consulte também

[Planejando o acesso de usuário externo](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Implantando o acesso de usuário externo](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)