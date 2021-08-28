---
title: Atualizar o certificado de borda
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: Este apêndice inclui etapas detalhadas para atualizar o certificado de borda como parte da consolidação de nuvem para Teams e Skype for Business.
ms.openlocfilehash: 1c4708f593b1a9bd8fbc2a427e2f0c5df9feab5c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610198"
---
# <a name="update-the-edge-certificate"></a>Atualizar o certificado de borda

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Atualizar o certificado de borda é a etapa fundamental para garantir que um ambiente local com SipDomain1 possa ingressar em um ambiente de nuvem com SipDomain2 e garantir o roteamento adequado em um ambiente de espaço de endereço compartilhado entre os dois domínios SIP. Consulte a etapa 14 em [Consolidação](cloud-consolidation.md) de nuvem para Teams e Skype for Business contexto no qual você pode executar esta etapa. Em nossos exemplos, SipDomain1 é AcquiredCompany. <span> com e SipDomain2 é OriginalCompany. <span> com.

O nome alternativo do assunto (SAN) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP existentes no locatário online puro (excluindo qualquer onmicrosoft. <span> domínios com), no formato "sip. \<domain> ".  Em nosso exemplo, isso é sip. OriginalCompany. <span> com. Esta etapa é fundamental antes de migrar qualquer usuário para a nuvem.

**Passos:**

1.  Obtenha um novo certificado de Borda Externa para a borda que tenha todas as entradas existentes mais entradas adicionais na SAN para todos os domínios SIP no ambiente de nuvem (excluindo *.onmicrosoft.com domínios) no formato "sip. <DomainName> ".
2.  Instale o certificado localmente em cada servidor de borda e atribua-o ao serviço Skype Edge em cada um dos serviços de borda.  Para etapas detalhadas, consulte a seção "Certificados de interface de borda externa" em [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).
3.  Reinicie o serviço de Borda em cada um dos servidores de borda. Você pode fazer isso por uma única caixa com os seguintes comandos do PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)