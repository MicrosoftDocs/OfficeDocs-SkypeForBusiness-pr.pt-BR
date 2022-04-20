---
title: Visão geral da certificação de aplicativos pela Microsoft
ms.reviewer: ''
description: Entenda os programas de certificação e atestado de aplicativos para aplicativos do Teams.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a8edd0afc2adde7a6867242dd0bdc0b406ca682
ms.sourcegitcommit: 745d707ec63685ce7f973785e7056628472b9c45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2022
ms.locfileid: "64910907"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>Programa de conformidade de aplicativos do Microsoft 365 para segurança, conformidade e privacidade de aplicativos de terceiros

O programa de conformidade da Microsoft verifica e audita um aplicativo em relação aos controles derivados das principais estruturas padrão do setor. O programa demonstra que existem fortes práticas de segurança e conformidade para proteger os dados dos clientes. O programa tem as seguintes fases:

* Verificação do publicador.
* Atestado do fornecedor.
* Certificação Microsoft 365.

## <a name="publisher-verification"></a>Verificação do fornecedor

Antes que um desenvolvedor de aplicativos possa enviar seu aplicativo para a Microsoft, é necessário que o desenvolvedor seja submetido a uma verificação. Um publicador verifica sua identidade usando sua conta do Microsoft Partner Network (MPN) e associa essa conta MPN ao registro do aplicativo. A verificação do publicador ajuda os administradores e usuários finais a entender a autenticidade dos desenvolvedores de aplicativos. A verificação do fornecedor oferece os seguintes benefícios:

* Maior transparência e redução de riscos para os clientes - essa funcionalidade ajuda os clientes a entender quais aplicativos que estão sendo usados nas suas organizações foram publicados por desenvolvedores nos quais eles confiam.
* Identidade visual aprimorada - um selo `verified` aparece no prompt de consentimento do Microsoft Azure AD, na página Aplicativos Corporativos e em outras interfaces de usuário usadas por usuários finais e administradores.
* Adoção empresarial mais suave - os administradores podem configurar as políticas de consentimento do usuário, com o status de verificação do fornecedor como critério principal da política.

## <a name="publisher-attestation"></a>Atestado do fornecedor

O atestado do fornecedor é o próximo nível no programa de conformidade de aplicativos. Os aplicativos atestados pelo publicador fornecem confiança aos administradores sobre as medidas de segurança e conformidade de um aplicativo. Isso também ajuda a reduzir o tempo de revisão dessas informações para um aplicativo. O atestado refletirá as práticas de segurança, tratamento de dados e conformidade de um aplicativo em relação a mais de 80 fatores de risco identificados pelo [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security). O processo de atestado do publicador pode ser iniciado antes da conclusão da verificação do Publicador.

Os desenvolvedores de aplicativos devem concluir uma autoavaliação que inclua perguntas frequentes feitas por clientes e administradores de TI para avaliar a segurança e a conformidade de um aplicativo. Em seguida, a Microsoft publica estas informações para uma avaliação mais fácil e oportuna. Para saber mais, consulte o [Guia de atestado](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

Os administradores podem verificar rapidamente os aplicativos atestados publicados de três maneiras diferentes.

* Ao coletar mais informações sobre um aplicativo, consulte os detalhes de um aplicativo específico em seu link em [segurança e conformidade de aplicativos do Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps). Como alternativa, selecione o link de atestado do Publicador no Centro de administração do Teams.

  :::image type="content" source="media/attested-app-tac3.png" alt-text="No Centro de administração do Teams, clique no link Atestado do Fornecedor para ver os detalhes do atestado de um aplicativo":::

* No Centro de administração do Teams, ao verificar os detalhes de um aplicativo na página **Gerenciar Aplicativo**, consulte o ícone atestado pelo fornecedor na faixa na página de detalhes do aplicativo.

  :::image type="content" source="media/attested-app-tac1.png" alt-text="No Centro de administração do Teams, o ícone Atestado pelo Fornecedor é exibido em todos os aplicativos atestados.":::

* No Centro de administração do Teams, ao conceder permissões ao aplicativo, uma marca de seleção azul na frente do nome do aplicativo indica um aplicativo atestado pelo editor ou um Microsoft 365 certificado.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="No Centro de administração do Teams, na caixa de diálogo para conceder permissões, a marca de seleção azul indica o aplicativo atestado pelo publicador.":::

A página de detalhes do atestado para um aplicativo atestado ou certificado lista os seguintes detalhes.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Informações detalhadas fornecidas para aplicativos atestados.":::

## <a name="microsoft-365-certification"></a>Certificação Microsoft 365

A certificação de aplicativo é obtida por meio de:

* Análise de um analista qualificado.
* Aprovação de uma avaliação abrangente centralizando estruturas, processos e procedimentos de segurança e conformidade de um aplicativo.

Verificamos o aplicativo em relação a uma série de controles de segurança derivados das principais estruturas padrão do setor.

O certificado demonstra que existem fortes práticas de segurança e conformidade para proteger os dados do cliente quando o aplicativo é ativado em uma organização. Mais informações sobre como a certificação Microsoft 365 é útil para administradores e usuários finais estão disponíveis em Visão geral do [programa de conformidade de aplicativos do Microsoft 365](/microsoft-365-app-certification/docs/enterprise-app-certification-guide).

Os administradores podem verificar rapidamente se há aplicativos certificados pelo Microsoft 365 das seguintes maneiras.

* Ao coletar mais informações sobre um aplicativo na Web, consulte o ícone de escudo na documentação da Microsoft sobre o aplicativo.

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="Exibir informações sobre a certificação Microsoft 365 no artigo de ajuda detalhado sobre segurança e conformidade de um aplicativo.":::

* Ao verificar um aplicativo no Centro de administração do Teams, classifique a lista de aplicativos usando a coluna Certificação. Veja o ícone e, opcionalmente, selecione o link para acessar a página específica do aplicativo mencionada acima.

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Exibir o status da certificação Microsoft 365 de um aplicativo no Centro de administração do Teams." lightbox="media/m365cert-apps-list2.png":::

* Ao visualizar os detalhes de um aplicativo, consulte o ícone certificado pelo Microsoft 365 na faixa do aplicativo.

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Exibir informações sobre a certificação Microsoft 365 na faixa do aplicativo ao gerenciar um aplicativo específico no Centro de administração do Teams ":::

* No Centro de administração do Teams, ao conceder permissões ao aplicativo, uma marca de seleção azul na frente do nome do aplicativo indica um aplicativo atestado pelo editor ou um Microsoft 365 certificado.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="No Centro de administração do Teams, na caixa de diálogo para conceder permissões, os administradores podem verificar a marca de seleção azul para ter certeza de que o aplicativo é certificado pelo Microsoft 365.":::

## <a name="view-security-compliance-and-privacy-information-in-microsoft-documentation"></a>Exibir informações de segurança, conformidade e privacidade na documentação da Microsoft

Para um aplicativo atestado ou certificado, os detalhes sobre segurança, privacidade, conformidade e muito mais para cada aplicativo estão listados nos artigos de ajuda específicos do aplicativo vinculados a [Segurança e conformidade de aplicativos do Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Informações detalhadas fornecidas para aplicativos que passam pelo programa de conformidade da Microsoft.":::

<!--- TBD: Move to the permissions article 

## View the granted Graph permissions in Azure Portal

Admins can grant permission to an app on behalf of all organization users. It helps avoid each user to individually request the permissions. Permissions granted of an admin are called delegated permissions in [Azure Portal](https://aad.portal.azure.com/).

Before you grant any permission to an app, review a list of requested permissions in the [Manage Apps](https://admin.teams.microsoft.com/policies/manage-apps) section of Teams admin center.

:::image type="content" source="media/attested-app-tac2.png" alt-text="In Teams admin center, on the dialog to grant permissions, admins can check the permissions requested by an app.":::

After admins grant the org-wide permissions to an app, they can review the Graph permissions in Azure Portal.

:::image type="content" source="media/tac-perms-in-aad-after-granting1.png" alt-text="Admins can see all the app permissions granted by users and admins in the Azure Portal." lightbox="media/tac-perms-in-aad-after-granting2.png":::
--->

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>Exibir a política de privacidade e os termos de uso de um aplicativo

No Centro de administração do Teams, cada página do aplicativo vincula-se à política de privacidade e aos termos de uso do aplicativo.

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="No Centro de administração do Teams, os administradores podem acessar o link para a política de privacidade e os termos de uso de todos os aplicativos." lightbox="media/tac-app-tou-privacy-info2.png":::

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

- How to view the support information for an app in TAC?

- We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->

## <a name="see-also"></a>Confira também

* [Exiba permissões do aplicativo e conceder consentimento do administrador](app-permissions-admin-center.md).
