---
title: Novidades do Roteamento Direto
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Este artigo descreve as novidades do Roteamento Direto. Verifique com frequência se há atualizações.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 8db0f0c4d29f786166098587aafc3ec1db256e38
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271456"
---
# <a name="whats-new-for-direct-routing"></a>Novidades do Roteamento Direto

Este artigo descreve as novidades do Roteamento Direto. Verifique com frequência se há atualizações.

## <a name="sip-support"></a>Suporte sip

Em 1º de junho de 2022, a Microsoft removerá o suporte para FQDNs de sip-all.pstnhub.microsoft.com e sip-all.pstnhub.gov.teams.microsoft.us da configuração de Roteamento Direto.

Se nenhuma ação for executada antes de 1º de junho, os usuários não poderão fazer ou receber chamadas por meio do Roteamento Direto.

Para evitar o impacto no serviço:

- Use as sub-redes recomendadas: (52.112.0.0/14 e 52.120.0.0/14) para qualquer classificação ou regras de ACL.
- Descontinue o uso do FQDN sip-all ao configurar controles de borda de sessão para roteamento direto.

Para obter mais informações, consulte [Planejar o Roteamento Direto](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificados TLS

O Microsoft 365 está atualizando o Teams e outros serviços para usar um conjunto diferente de ACs (Autoridades de Certificação Raiz).

Para obter mais informações e uma lista completa dos serviços afetados, confira as alterações [de certificado TLS nos serviços do Microsoft 365, incluindo o Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Autoridades de certificação

A partir de 1º de fevereiro de 2022, a interface SIP de Roteamento Direto confiará apenas em certificados assinados por autoridades de certificação (CAs) que fazem parte do Programa de Certificado Raiz Confiável da Microsoft. Execute as seguintes etapas para evitar o impacto no serviço:

- Verifique se o certificado SBC foi assinado por uma AC que faz parte do Programa de Certificado Raiz Confiável da Microsoft.
- Verifique se a extensão EKU (Uso Estendido de Chave) do certificado inclui "Autenticação de Servidor".

Para obter mais informações sobre o Programa de Certificado Raiz Confiável da Microsoft, consulte [Requisitos do Programa – Programa Raiz Confiável da Microsoft](/security/trusted-root/program-requirements).

Para obter uma lista de AC confiável, consulte a [Lista de Certificados de Autoridade de Certificação incluída da Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Substituir cabeçalhos

A partir de abril de 2022, o Roteamento Direto rejeitará solicitações SIP que têm cabeçalhos Replaces definidos. Não há alterações nos fluxos em que a Microsoft envia o cabeçalho Replaces para o controlador de borda de sessão (SBC).

Verifique suas configurações de SBC e verifique se você não está usando cabeçalhos Replaces em solicitações SIP.

## <a name="tls10-and-11"></a>TLS1.0 e 1.1

Para fornecer a melhor criptografia de classe para nossos clientes, a Microsoft planeja substituir as versões 1.0 e 1.1 do Protocolo TLS. Em 3 de abril de 2022, a Microsoft forçará o uso do TLS1.2 para a interface SIP de Roteamento Direto.

Para evitar qualquer impacto no serviço, verifique se os SBCs estão configurados para dar suporte ao TLS1.2 e se podem se conectar usando um dos seguintes conjuntos de criptografia:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 ou seja, ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 ou seja, ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 ou seja, ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 ou seja, ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Tópicos relacionados

- [Roteamento direto – protocolo SIP](direct-routing-protocols-sip.md)
