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
description: Este apêndice inclui etapas detalhadas para atualizar o certificado de borda como parte da consolidação na nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888600"
---
# <a name="update-the-edge-certificate"></a>Atualizar o certificado de borda

Atualizar o certificado de borda é a etapa principal para garantir que um ambiente local com SipDomain1 possa ingressar em um ambiente de nuvem com SipDomain2 e garantir o roteamento adequado em um ambiente de espaço de endereço compartilhado entre os dois domínios SIP. Confira a etapa 14 na [consolidação na nuvem](cloud-consolidation.md) para o Teams e o Skype for Business para contexto no qual você pode executar esta etapa. Em nossos exemplos, SipDomain1 é AcquiredCompany. <span> com e SipDomain2 é OriginalCompany. <span> com.

O san (nome alternativo da assunto) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP existentes no locatário online puro (excluindo qualquer onmicrosoft. <span> domínios com), no formato "sip. \< domain>".  No nosso exemplo, isso é sip. OriginalCompany. <span> com. Esta etapa é fundamental antes de migrar qualquer usuário para a nuvem.

**Etapas:**

1.  Obtenha um novo certificado de Borda Externa para a borda que tenha todas as entradas existentes mais entradas adicionais no SAN para todos os domínios SIP no ambiente de nuvem (excluindo domínios *.onmicrosoft.com) no formato <DomainName> "sip".
2.  Instale o certificado localmente em cada servidor de borda e atribua-o ao serviço de Borda do Skype em cada serviço de borda.  Para etapas detalhadas, consulte a seção "Certificados da interface de Borda Externa" em Implantar Serviço de Borda no [Skype for Business Server 2015.](https://technet.microsoft.com/library/dn951368.aspx)
3.  Reinicie o serviço de Borda em cada um dos servidores de borda. Você pode fazer isso para uma única caixa com os seguintes comandos do PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Confira também

[Consolidação na nuvem para o Teams e o Skype for Business](cloud-consolidation.md)