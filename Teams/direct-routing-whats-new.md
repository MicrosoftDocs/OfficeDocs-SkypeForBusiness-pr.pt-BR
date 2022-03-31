---
title: O que há de novo roteamento direto
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Este artigo descreve as novidades no Roteamento Direto. Verifique com frequência atualizações.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6f2ec21ec3e7f4278443d6bcab4b4220db3619f
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556732"
---
# <a name="whats-new-for-direct-routing"></a>Novidades para Roteamento Direto

Este artigo descreve as novidades no Roteamento Direto. Verifique com frequência atualizações.

## <a name="sip-support"></a>Suporte SIP

Em 1º de junho de 2022, a Microsoft removerá o suporte para sip-all.pstnhub.microsoft.com e sip-all.pstnhub.gov.teams.microsoft.us FQDNs da configuração de Roteamento Direto.

Se nenhuma ação for tomada antes de 1º de junho, os usuários não poderão fazer ou receber chamadas via Roteamento Direto.

Para evitar o impacto no serviço:

- Use as sub-redes recomendadas: (52.112.0.0/14 e 52.120.0.0/14) para qualquer classificação ou regras ACL.
- Interrompa o uso do FQDN sip-all ao configurar controles de borda de sessão para roteamento direto.

Para obter mais informações, consulte [Plan Direct Routing](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificados TLS

Microsoft 365 está atualizando Teams e outros serviços para usar um conjunto diferente de autoridades de certificado raiz (CAs).

Para obter mais informações e uma lista completa de serviços afetados, consulte Alterações de certificado [TLS](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676) em serviços Microsoft 365 incluindo Microsoft Teams.

## <a name="certificate-authorities"></a>Autoridades de certificados

A partir de 1º de fevereiro de 2022, a interface SIP de Roteamento Direto confiará apenas em certificados assinados por autoridades de certificação (CAs) que fazem parte do Programa de Certificado Raiz Confiável da Microsoft. Tome as seguintes etapas para evitar o impacto no serviço:

- Verifique se o certificado SBC foi assinado por uma AC que faz parte do Programa de Certificado Raiz Confiável da Microsoft.
- Verifique se a extensão uso de chave estendida (EKU) do certificado inclui "Autenticação do Servidor".

Para obter mais informações sobre o Programa de Certificado Raiz Confiável da Microsoft, consulte [Requisitos de Programas - Programa Raiz Confiável da Microsoft](/security/trusted-root/program-requirements).

Para uma lista de acções confiáveis, consulte [Lista de certificados de AC incluídos pela Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Substituir os headers

A partir de abril de 2022, o Roteamento Direto rejeitará solicitações SIP que tenham os headers Replaces definidos. Não há alterações nos fluxos em que a Microsoft envia o header Replaces para o Controlador de Borda de Sessão(SBC).

Verifique suas configurações SBC e verifique se você não está usando os headers Replaces em solicitações SIP.

## <a name="tls10-and-10"></a>TLS1.0 e 1.0

Para fornecer a melhor criptografia em classe para nossos clientes, a Microsoft planeja preprecar as versões 1.0 e 1.1 do TLS (Transport Layer Security). Em 3 de abril de 2022, a Microsoft força o uso do TLS1.2 para a interface SIP de Roteamento Direto.

Para evitar qualquer impacto no serviço, certifique-se de que seus SBCs estão configurados para dar suporte a TLS1.2 e podem se conectar usando um dos seguintes pacote de codificação:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 ou seja, ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 ou seja, ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 ou seja, ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 ou seja, ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Tópicos relacionados

- [Roteamento Direto - protocolo SIP](direct-routing-protocols-sip.md)
