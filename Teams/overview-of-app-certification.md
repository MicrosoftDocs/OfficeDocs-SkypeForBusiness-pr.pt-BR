---
title: Visão geral da certificação de aplicativos pela Microsoft
description: Saiba mais sobre o programa de conformidade de aplicativos do Microsoft 365 para segurança, conformidade e privacidade de aplicativos de terceiros.
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 09/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 992b557e72aaa855008f1bfec8073d800b65badf
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377539"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>Programa de conformidade de aplicativos do Microsoft 365 para segurança, conformidade e privacidade de aplicativos de terceiros

O programa de conformidade da Microsoft verifica e audita um aplicativo em relação aos controles derivados das principais estruturas padrão do setor. O programa demonstra que existem fortes práticas de segurança e conformidade para proteger os dados dos clientes. O programa tem as seguintes fases:

* [Verificação do publicador](#publisher-verification).
* [Atestado do publicador](#publisher-attestation).
* [Certificação do Microsoft 365](#microsoft-365-certification).

## <a name="publisher-verification"></a>Verificação do fornecedor

Antes que um desenvolvedor de aplicativos possa enviar seu aplicativo para a Microsoft, é necessário que o desenvolvedor seja submetido a uma verificação. Um desenvolvedor verifica sua identidade usando sua conta do Microsoft Partner Network (MPN) e associa essa conta MPN ao registro do aplicativo. A verificação do publicador ajuda os administradores e usuários finais a entender a autenticidade dos desenvolvedores de aplicativos. A verificação do fornecedor oferece os seguintes benefícios:

* Maior transparência e redução de riscos para os clientes - essa funcionalidade ajuda os clientes a entender quais aplicativos que estão sendo usados nas suas organizações foram publicados por desenvolvedores nos quais eles confiam.
* Identidade visual aprimorada - um selo `verified` aparece no prompt de consentimento do Microsoft Azure AD, na página Aplicativos Corporativos e em outras interfaces de usuário usadas por usuários finais e administradores.
* Adoção empresarial mais suave - os administradores podem configurar as políticas de consentimento do usuário, com o status de verificação do fornecedor como critério principal da política.

## <a name="publisher-attestation"></a>Atestado do fornecedor

O atestado do fornecedor é o próximo nível no programa de conformidade de aplicativos. Os aplicativos atestados pelo publicador fornecem confiança aos administradores sobre as medidas de segurança e conformidade de um aplicativo. Isso também ajuda a reduzir o tempo de revisão dessas informações para um aplicativo. O atestado refletirá as práticas de segurança, tratamento de dados e conformidade de um aplicativo em relação a mais de 80 fatores de risco identificados pelo [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security). O processo de atestado do publicador pode ser iniciado antes da conclusão da verificação do Publicador.

Os desenvolvedores de aplicativos devem concluir uma autoavaliação que inclua perguntas frequentes feitas por clientes e administradores de TI para avaliar a segurança e a conformidade de um aplicativo. Em seguida, a Microsoft publica estas informações para uma avaliação mais fácil e oportuna. Para saber mais, consulte o [Guia de atestado](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

Os administradores podem verificar rapidamente os aplicativos atestados publicados de três maneiras diferentes.

* Ao coletar mais informações sobre um aplicativo, consulte os detalhes de um aplicativo específico no seu link em [Segurança e conformidade de aplicativos do Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps). Como alternativa, selecione o link `Publisher attestation` no [Centro de administração do Teams](https://admin.teams.microsoft.com/).

  :::image type="content" source="media/attested-app-tac3.png" alt-text="No Centro de administração do Teams, selecione o link Atestado do Fornecedor para ver os detalhes do atestado de um aplicativo.":::

* No Centro de administração do Teams, ao verificar os detalhes de um aplicativo na página **[Gerenciar Aplicativo](https://admin.teams.microsoft.com/policies/manage-apps)**, consulte o ícone atestado pelo fornecedor na faixa na página de detalhes do aplicativo.

  :::image type="content" source="media/attested-app-tac1.png" alt-text="No Centro de administração do Teams, o ícone Atestado pelo Fornecedor é exibido em todos os aplicativos atestados.":::

* No Centro de administração do Teams, antes de conceder permissões ao [aplicativo, uma](app-permissions-admin-center.md) marca de seleção azul na frente do nome do aplicativo indica que é um aplicativo atestado pelo editor. Todos os aplicativos do Microsoft 365 também passam pelo atestado do editor, portanto, uma marca de seleção azul também é exibida para aplicativos do Microsoft 365.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="No Centro de administração do Teams, na caixa de diálogo para conceder permissões, a marca de seleção azul indica o aplicativo atestado pelo publicador.":::

A página de detalhes do atestado para um aplicativo atestado ou certificado lista os seguintes detalhes.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Informações detalhadas fornecidas para aplicativos atestados.":::

## <a name="microsoft-365-certification"></a>Certificação Microsoft 365

A certificação de aplicativo é obtida por meio de:

* Análise de um analista qualificado.
* Aprovação de uma avaliação abrangente centralizando estruturas, processos e procedimentos de segurança e conformidade de um aplicativo.

Verificamos o aplicativo em relação a uma série de controles de segurança derivados das principais estruturas padrão do setor.

O certificado demonstra as fortes práticas de segurança e conformidade que estão em vigor para proteger os dados do cliente quando o aplicativo é usado em uma organização. Mais informações sobre como os administradores e usuários finais se beneficiam da certificação estão disponíveis em [Visão geral do Programa de conformidade de aplicativos do Microsoft 365](/microsoft-365-app-certification/docs/enterprise-app-certification-guide).

Os administradores podem verificar rapidamente se há aplicativos certificados pelo Microsoft 365 das seguintes maneiras.

* Ao coletar mais informações sobre um aplicativo na Web, consulte o ícone de escudo na [documentação da Microsoft sobre o aplicativo](/microsoft-365-app-certification/teams/teams-apps).

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="Veja as informações sobre a Certificação do Microsoft 365 no artigo de ajuda detalhado sobre segurança e conformidade de um aplicativo":::

* Ao verificar um aplicativo no [Centro de administração do Teams](https://admin.teams.microsoft.com/policies/manage-apps), classifique a lista de aplicativos usando a coluna Certificação. Veja o ícone e, opcionalmente, selecione o link para acessar a página específica do aplicativo mencionada acima.

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Exibir o status da certificação Microsoft 365 de um aplicativo no Centro de administração do Teams." lightbox="media/m365cert-apps-list2.png":::

* Ao visualizar os detalhes de um aplicativo, consulte o ícone certificado pelo Microsoft 365 na faixa do aplicativo.

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Exibir informações sobre a certificação Microsoft 365 na faixa do aplicativo ao gerenciar um aplicativo específico no Centro de administração do Teams ":::

* No Centro de administração do Teams, antes de conceder permissões ao [aplicativo, uma](app-permissions-admin-center.md) marca de seleção azul na frente do nome do aplicativo indica que é um aplicativo atestado pelo editor. Todos os aplicativos do Microsoft 365 também passam pelo atestado do editor, portanto, uma marca de seleção azul também é exibida para aplicativos do Microsoft 365.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="No centro de administração do Teams, na caixa de diálogo para conceder permissões, os administradores podem verificar a marca de seleção azul para ter certeza de que o aplicativo é Certificado pelo Microsoft 365":::

## <a name="view-security-compliance-and-privacy-information"></a>Exibir informações de segurança, conformidade e privacidade

Você pode encontrar informações sobre segurança, privacidade, conformidade e comportamentos para um aplicativo atestado ou certificado na [documentação da Microsoft](/microsoft-365-app-certification/teams/teams-apps) e no [Centro de Administração do Teams](https://admin.teams.microsoft.com/policies/manage-apps).

### <a name="microsoft-documentation"></a>Documentação da Microsoft

Você pode encontrar os detalhes sobre segurança, privacidade, conformidade e muito mais para cada aplicativo listado nos artigos de ajuda específicos do aplicativo vinculado da [Segurança e Conformidade dos Aplicativos do Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Informações detalhadas fornecidas para aplicativos que passam pelo programa de conformidade da Microsoft.":::

### <a name="teams-admin-center"></a>Centro de administração do Teams

Ao avaliar um aplicativo, você pode usar Agentes de Segurança de Acesso à Nuvem (CASB) independentes, como o Microsoft Cloud App Security (MCAS), para encontrar informações sobre a segurança e os comportamentos de um aplicativo. O centro de administração do Teams inclui informações de conformidade e segurança do MCAS para aplicativos Certificados pelo Microsoft 365. Verifique essas informações na página de detalhes do aplicativo para verificar se o aplicativo atende às suas necessidades de segurança.

> [!NOTE]
> Este recurso está disponível para todos os administradores, independentemente da sua organização ter ou não uma licença que suporte o MCAS.

Para acesso as informações do MCAS de um aplicativo:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Selecione **Certificação** para classificar os aplicativos e empurrar todos os aplicativos Certificados pelo Microsoft 365 para o topo da tabela.

1. Escolha um aplicativo Certificado pelo Microsoft 365.

1. Selecione a guia **Segurança e conformidade**.

   :::image type="content" source="media/mcas.png" alt-text="Captura de tela da guia de segurança e conformidade do Centro de administração do Teams.":::

   Para obter mais detalhes sobre as funcionalidades suportadas pelo aplicativo, selecione a lista suspensa para cada categoria.

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>Exibir a política de privacidade e os termos de uso de um aplicativo

No Centro de administração do Teams, cada página do aplicativo vincula-se à política de privacidade e aos termos de uso do aplicativo.

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="No Centro de administração do Teams, os administradores podem acessar o link para a política de privacidade e os termos de uso de todos os aplicativos." lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>Artigos relacionados

* [Exiba permissões do aplicativo e conceder consentimento do administrador](app-permissions-admin-center.md).
