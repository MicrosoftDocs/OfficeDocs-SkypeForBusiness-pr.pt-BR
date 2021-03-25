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
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para atualizar o certificado de borda como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120340"
---
# <a name="update-the-edge-certificate"></a>Atualizar o certificado de borda

Atualizar o certificado de borda é a etapa fundamental para garantir que um ambiente local com SipDomain1 possa ingressar em um ambiente de nuvem com SipDomain2 e garantir o roteamento adequado em um ambiente de espaço de endereço compartilhado entre os dois domínios SIP. Consulte a etapa 14 em [Consolidação de](cloud-consolidation.md) nuvem para o Teams e o Skype for Business para contexto no qual você pode executar esta etapa. Em nossos exemplos, SipDomain1 é AcquiredCompany. <span> com e SipDomain2 é OriginalCompany. <span> com.

O nome alternativo do assunto (SAN) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP existentes no locatário online puro (excluindo qualquer onmicrosoft. <span> domínios com), no formato "sip. \<domain> ".  Em nosso exemplo, isso é sip. OriginalCompany. <span> com. Esta etapa é fundamental antes de migrar qualquer usuário para a nuvem.

**Etapas:**

1.  Obtenha um novo certificado de Borda Externa para a borda que tenha todas as entradas existentes mais entradas adicionais na SAN para todos os domínios SIP no ambiente de nuvem (excluindo *.onmicrosoft.com domínios) no formato "sip. <DomainName> ".
2.  Instale o certificado localmente em cada servidor de borda e atribua-o ao serviço de Borda do Skype em cada um dos serviços de borda.  Para etapas detalhadas, consulte a seção "Certificados de interface de borda externa" em [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).
3.  Reinicie o serviço de Borda em cada um dos servidores de borda. Você pode fazer isso por uma única caixa com os seguintes comandos do PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)