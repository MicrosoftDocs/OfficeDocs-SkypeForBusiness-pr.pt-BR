---
title: Atualizar o certificado de borda
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui as etapas detalhadas para atualizar o certificado de borda como parte da consolidação de nuvem para equipes e Skype para negócios.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247594"
---
# <a name="update-the-edge-certificate"></a>Atualizar o certificado de borda

Atualizar o certificado de borda é a etapa de chave para garantir que um ambiente em prem com SipDomain1 pode ingressar em um ambiente de nuvem com SipDomain2 e garantir o roteamento apropriado em um ambiente de espaço de endereçamento compartilhado entre os dois domínios SIP. Consulte a etapa 14 da [consolidação de nuvem para equipes e Skype para negócios](cloud-consolidation.md) de contexto no qual você pode executar esta etapa. Em nossos exemplos, SipDomain1 é AcquiredCompany. <span>SipDomain2 e com é OriginalCompany. <span>com.

Nome alternativo da entidade (SAN) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP que existem no locatário online puro (excluindo qualquer onmicrosoft.<span> domínios com), no formato "sip. \<domínio > ".  No nosso exemplo, este é o sip. OriginalCompany. <span>com. Esta etapa é fundamental para fazer antes de migrar todos os usuários para a nuvem.

**Etapas:**

1.  Obter um novo certificado de borda externa da borda que tenha todas as suas entradas plus entradas adicionais no SAN para todos os domínios SIP no ambiente de nuvem (excluindo *. onmicrosoft.com domínios) no formato "sip. <DomainName>".
2.  Instale o certificado localmente em cada servidor de borda e atribuí-lo para o serviço de borda do Skype em cada um do serviço de borda.  Para obter etapas detalhadas, consulte a seção "Certificados de interface de borda externa" em [Implantar o serviço de borda no Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).
3.  Reinicie o serviço de borda em cada um dos servidores de borda. Você pode fazer isso para uma única caixa com os seguintes comandos do PowerShell:

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Consulte também

[Consolidação de nuvem para equipes e Skype para negócios](cloud-consolidation.md)