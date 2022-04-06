---
title: Visão geral da validação de aplicativos e testes de aplicativos pela Microsoft
ms.reviewer: ''
description: Entenda as verificações de qualidade, a validação de aplicativos e os programas de certificação para Teams aplicativos.
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
ms.openlocfilehash: 384a57abb724ee29feb5f93fa171d0bc5ec96f3d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686488"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Verificações e validação executadas pela Microsoft em Teams aplicativos

A Microsoft exige que todos os aplicativos passem por uma validação obrigatória antes de serem listados na loja para usos finais. Ela se aplica a todos os aplicativos (exceto aplicativos personalizados) publicados na Teams App Store. Além disso, a Microsoft incentiva fortemente os desenvolvedores de aplicativos a participar de uma certificação opcional de aplicativos que indica controles de conformidade, segurança e privacidade aprimorados.

Todos os aplicativos são obrigatórios para aderir às políticas de Certificação de Aplicativos da Microsoft. A Teams da loja realiza mais de 400 testes para garantir que os aplicativos sejam utilizáveis e aderam aos altos padrões de privacidade e segurança.

Para conhecer as diretrizes de validação detalhadas que os desenvolvedores de aplicativos seguem, consulte [as diretrizes de validação para desenvolvedores](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). As diretrizes se baseiam nas políticas [de certificação para Teams aplicativos](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> A validação e as verificações da Microsoft não estão disponíveis para um aplicativo personalizado, pois ele é desenvolvido em sua organização e só está disponível para membros da sua organização.

## <a name="app-validation-and-testing"></a>Validação e teste de aplicativo

Executamos mais de 400 casos de teste para cada aplicativo antes que ele seja disponibilizado na Teams Store. Os testes garantem a funcionalidade apropriada, a experiência do usuário e a segurança e garantem que todos os aplicativos estão em conformidade com as políticas de CMO listadas publicamente. A seguir estão alguns dos testes realizados pela equipe de Validação de Aplicativos da Microsoft para cada aplicativo antes de ser publicado:

* Verifique se Graph permissões solicitadas pelo aplicativo são realmente aquelas de que a funcionalidade do aplicativo precisa e não nenhuma permissão extra. Graph permissões para aplicativos existentes são verificadas regularmente para garantir que nenhuma permissão extra seja exigida por um aplicativo.
* Os aplicativos que exigem que os usuários façam logon/se conectem devem ter uma opção de logon/saída.
* Todos os editores de aplicativos passam por um processo de verificação detalhado no Microsoft Partner Center. A verificação inclui verificação de email, verificação de negócios e muito mais. Para saber mais sobre a publicação de aplicativos, consulte Como os desenvolvedores criam uma conta do [Partner Center](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)[, o](/office/dev/store/add-in-submission-guide) guia de envio para desenvolvedores e [como os desenvolvedores publicam aplicativos](https://aka.ms/PublishToTeamsStore).
* Somente aplicativos de editores verificados podem buscar Graph permissões de usuários finais.
* Nenhum aplicativo pode baixar um arquivo executável.
* Os aplicativos são testados para não conter anúncios, promoção para outros aplicativos
* Os aplicativos são testados para funcionar adequadamente sem linguagem ofensiva, bots de ataque cibernético, spam ou conteúdo de fraude.
* Todos os links em um aplicativo são funcionais e relacionados apenas à oferta de aplicativo.
* Testamos e avaliamos todos os aplicativos Teams publicados regularmente como parte das verificações de integridade da loja de aplicativos.
* Política de privacidade e Termos de uso que abrangem Teams aplicativos são publicados pelo ISV
* Os detalhes de contato do ISV estão disponíveis na listagem da loja e em suas respectivas [Publisher de Atestado](/microsoft-365-app-certification/teams/teams-apps).

## <a name="publisher-verification"></a>Publisher verificação

Publisher verificação ajuda administradores e usuários finais a entender a autenticidade dos desenvolvedores de aplicativos que se integram ao plataforma de identidade da Microsoft. Ter um editor verificado significa que o editor verificou sua identidade usando sua conta do MPN (Microsoft Partner Network) e associou essa conta do MPN ao registro do aplicativo.

Publisher verificação fornece os seguintes benefícios:

* Maior transparência e redução de riscos para os clientes – essa funcionalidade ajuda os clientes a entender quais aplicativos que estão sendo usados em suas organizações são publicados pelos desenvolvedores em que confiam.
* Identidade visual aprimorada – `verified` uma notificação é exibida no prompt de Azure Active Directory de consentimento, Enterprise aplicativos e outras interfaces do usuário usadas por usuários finais e administradores.
* Adoção empresarial mais suave – os administradores podem configurar políticas de consentimento do usuário, com o status de verificação do editor como critérios de política primária.

Além disso, a Microsoft incentiva os desenvolvedores de aplicativos a participarem de seu programa de conformidade, que é uma abordagem rigorosa de duas camadas para garantir a qualidade, a segurança e a conformidade do aplicativo. Teams store tem centenas de aplicativos que vão além do cumprimento das diretrizes de validação já detalhadas e estão em conformidade com esses programas.

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365 de conformidade do aplicativo

O programa de conformidade da Microsoft demonstra que um aplicativo é avaliado contra controles derivados de estruturas padrão líderes do setor e que práticas fortes de segurança e conformidade estão em vigor para proteger os dados do cliente. O programa tem duas fases:

* Publisher atestado.
* Microsoft 365 certificação.

### <a name="publisher-attestation"></a>Publisher atestado

O desenvolvedor do aplicativo precisa concluir uma autoavaliação que inclui perguntas frequentes feitas por clientes ou administradores de TI ao avaliar a segurança e a conformidade de um aplicativo. Em seguida, a Microsoft publica essas informações para uma avaliação mais fácil e o tempo limite. As informações incluem detalhes sobre manipulação de dados, segurança, conformidade e privacidade quando um aplicativo é ativado em uma organização.

Para saber mais, confira o [guia Publicar atestado](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

### <a name="microsoft-365-certification"></a>Microsoft 365 certificação

A certificação de aplicativos é obtida por meio da revisão e aprovação de um analista qualificado de uma avaliação abrangente centralizando estruturas, processos e procedimentos de segurança e conformidade de um aplicativo. O aplicativo é avaliado em uma série de controles de segurança derivados de estruturas padrão líderes do setor. O certificado demonstra que práticas fortes de segurança e conformidade estão em vigor para proteger os dados do cliente quando o aplicativo é ativado em uma organização.

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
