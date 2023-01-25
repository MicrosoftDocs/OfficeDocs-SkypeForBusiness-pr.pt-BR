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
description: Este artigo descreve as novidades no Roteamento Direto. Verifique com frequência se há atualizações.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 87befd2ff63fc5e3f0aa9e1c715972e5061b8fc7
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981866"
---
# <a name="whats-new-for-direct-routing"></a>Novidades para Roteamento Direto

Este artigo descreve as novidades no Roteamento Direto. Verifique com frequência se há atualizações.

## <a name="new-direct-routing-sip-endpoints"></a>Novos pontos de extremidade SIP de Roteamento Direto 

A Microsoft apresentará novos IPs de sinalização aos pontos de extremidade SIP de Roteamento Direto do Teams. Para garantir que essa alteração não afete sua disponibilidade de serviço, verifique se o Controlador de Borda de Sessão e o Firewall estão configurados para usar as sub-redes recomendadas 52.112.0.0.0/14 e 52.120.0.0/14 para regras de classificação e ACL. Para obter mais informações, confira [Ambientes de GCC do Microsoft 365, Office 365 e Office 365](direct-routing-plan.md#microsoft-365-office-365-and-office-365-gcc-environments).  

## <a name="trunk-demoting-logic-based-on-sip-options"></a>Lógica de rebaixamento de tronco com base em Opções SIP

Um novo recurso baseado em Opções SIP é introduzido para a integridade do tronco. Quando habilitada na configuração do gateway (consulte Set-CsOnlinePSTNGateway parâmetro cmdlet e SendSipOptions), a lógica de roteamento para chamadas de saída rebaixa troncos que não enviam opções SIP periodicamente (o período esperado é uma opção SIP enviada pelo SBC por minuto) para o back-end da Microsoft. Esses troncos rebaixados são colocados no final da lista de troncos disponíveis para a chamada de saída e são testados como os últimos; assim, potencialmente, diminuindo o tempo de configuração da chamada.
Qualquer tronco habilitado para esse recurso que não envia pelo menos uma opção SIP dentro de cinco minutos para qualquer um dos Proxies SIP regionais da Microsoft (NOAM, EMEA, APAC, OCEA) é considerado rebaixado. Se um tronco enviar opções SIP para apenas um subconjunto de Proxies SIP regionais da Microsoft, essas rotas serão testadas primeiro e as restantes serão rebaixadas.


## <a name="sip-support"></a>Suporte ao SIP

Em 1º de junho de 2022, a Microsoft removerá o suporte para sip-all.pstnhub.microsoft.com e sip-all.pstnhub.gov.teams.microsoft.us FQDNs da configuração de Roteamento Direto.

Se nenhuma ação for tomada antes de 1º de junho, os usuários não poderão fazer ou receber chamadas por meio do Roteamento Direto.

Para evitar o impacto do serviço:

- Use as sub-redes recomendadas: (52.112.0.0/14 e 52.122.0.0/15) para qualquer classificação ou regras de ACL.
- Descontinue o uso do FQDN sip-all ao configurar controles de borda de sessão para roteamento direto.

Para obter mais informações, consulte [Planejar Roteamento Direto](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificados TLS

O Microsoft 365 está atualizando o Teams e outros serviços para usar um conjunto diferente de CAs (Autoridades de Certificado Raiz).

Para obter mais informações e uma lista completa de serviços afetados, confira [Alterações de certificado TLS nos serviços do Microsoft 365, incluindo o Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Autoridades de certificado

A partir de 1º de fevereiro de 2022, a interface SIP de Roteamento Direto confiará apenas em certificados assinados por CAs (Autoridades de Certificado) que fazem parte do Programa de Certificado Raiz Confiável da Microsoft. Siga as seguintes etapas para evitar o impacto do serviço:

- Verifique se o certificado SBC é assinado por uma AC que faz parte do Programa de Certificado Raiz Confiável da Microsoft.
- Verifique se a extensão EKU (Uso de Chave Estendida) do certificado inclui "Autenticação do Servidor".

Para obter mais informações sobre o Programa de Certificado Raiz Confiável da Microsoft, consulte [Requisitos do Programa – Programa Raiz Confiável da Microsoft](/security/trusted-root/program-requirements).

Para obter uma lista de ac confiáveis, consulte [Lista de certificados de AC incluídos pela Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Substituir cabeçalhos

A partir de abril de 2022, o Roteamento Direto rejeitará as solicitações SIP que têm cabeçalhos Replaces definidos. Não há alterações nos fluxos em que a Microsoft envia o cabeçalho Substituções para o SBC (Controlador de Borda de Sessão).

Verifique as configurações do SBC e verifique se você não está usando cabeçalhos Substitui em solicitações SIP.

## <a name="tls10-and-11"></a>TLS1.0 e 1.1

Para fornecer a melhor criptografia da classe para nossos clientes, a Microsoft planeja preterir as versões TLS (Transport Layer Security) 1.0 e 1.1. Em 3 de abril de 2022, a Microsoft forçará o uso do TLS1.2 para a interface SIP de Roteamento Direto.

Para evitar qualquer impacto no serviço, verifique se os SBCs estão configurados para dar suporte ao TLS1.2 e podem se conectar usando um dos seguintes pacotes de criptografia:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 ou seja, ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 ou seja, ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 ou seja, ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 ou seja, ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Tópicos relacionados

- [Roteamento Direto – protocolo SIP](direct-routing-protocols-sip.md)
