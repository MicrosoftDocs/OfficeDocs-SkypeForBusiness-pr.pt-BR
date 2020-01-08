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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para a atualização do certificado de borda como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 52ab646387acb6901798f215f9677f16978e87fb
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963049"
---
# <a name="update-the-edge-certificate"></a>Atualizar o certificado de borda

A atualização do certificado de borda é a etapa principal para garantir que um ambiente local com o SipDomain1 possa ingressar em um ambiente de nuvem com o SipDomain2 e garantir o roteamento adequado em um ambiente de espaço de endereçamento compartilhado nos dois domínios SIP. Confira a etapa 14 em [consolidação de nuvem para o Microsoft Teams e o Skype for Business](cloud-consolidation.md) para o contexto no qual você pode executar esta etapa. Nos nossos exemplos, SipDomain1 é AcquiredCompany. <span>com e SipDomain2 é OriginalCompany. <span>com.

O nome alternativo de entidade (SAN) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP existentes no locatário online puro (excluindo qualquer onmicrosoft.<span> Domínios com), no formato "SIP. \<> de domínio ".  No nosso exemplo, é SIP. OriginalCompany. <span>com. Esta etapa é crítica para fazer antes de migrar qualquer usuário para a nuvem.

**Necessárias**

1.  Obtenha um novo certificado de borda externo para a borda que tenha todas as entradas existentes, além de entradas adicionais na SAN para todos os domínios SIP no ambiente de nuvem (excluindo os domínios *. onmicrosoft.com) no formato "SIP. <DomainName>".
2.  Instale o certificado localmente em cada servidor de borda e atribua-o ao serviço de borda do Skype em cada um dos serviços de borda.  Para obter etapas detalhadas, consulte a seção "certificados de interface de borda externa" em [implantar serviço de borda no Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).
3.  Reinicie o serviço de borda em cada um dos servidores de borda. Você pode fazer isso para uma única caixa com os seguintes comandos do PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)
