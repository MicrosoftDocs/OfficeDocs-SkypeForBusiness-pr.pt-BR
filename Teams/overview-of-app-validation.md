---
title: Visão geral da validação de aplicativos e teste de aplicativos pela Microsoft
ms.reviewer: ''
description: Entenda as verificações de qualidade e a validação de aplicativos feitas para os aplicativos do Teams.
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
ms.openlocfilehash: fa6a03c5408afcd7cce1d3e48b78b3b1ddb3675a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/11/2022
ms.locfileid: "64756987"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Validação executada pela Microsoft para todos os aplicativos do Teams

A Microsoft exige que todos os aplicativos passem por uma validação obrigatória antes de serem listados na loja para uso final. Aplica-se a todos os aplicativos (exceto aplicativos personalizados) publicados na loja de Aplicativos do Teams. Além disso, a Microsoft incentiva fortemente os desenvolvedores de aplicativos a participarem de uma certificação opcional de aplicativos que indique controles avançados de conformidade, segurança e privacidade.

Todos os aplicativos são obrigatoriamente exigidos a aderirem às políticas de Certificação de Aplicativos da Microsoft. A equipe da loja do Teams realiza mais de 400 testes para garantir que os aplicativos sejam utilizáveis e cumpram altos padrões de privacidade e segurança.

Para conhecer as diretrizes detalhadas de validação às quais os desenvolvedores de aplicativos aderem, consulte [Diretrizes de validação para desenvolvedores](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). As diretrizes se baseiam nas [Políticas de certificação para aplicativos do Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> A validação e as verificações pela Microsoft não estão disponíveis para um aplicativo personalizado, pois ele é desenvolvido dentro da sua organização e só está disponível para membros da sua organização.

## <a name="app-validation-and-testing"></a>Validação e teste de aplicativos

Executamos mais de 400 casos de teste para cada aplicativo antes que ele seja disponibilizado na Teams Store. Os testes garantem funcionalidade, experiência do usuário e segurança adequadas, além de garantir que todos os aplicativos estejam em conformidade com as políticas de CMO listadas publicamente. A seguir estão alguns dos testes realizados pela equipe de validação de aplicativos da Microsoft para cada aplicativo antes de serem publicados:

* Certifique-se de que as permissões do Graph solicitadas pelo aplicativo são realmente as que a funcionalidade do aplicativo precisa e não quaisquer permissões extras. As permissões do Graph para aplicativos existentes são verificadas regularmente para garantir que nenhuma permissão extra seja necessária por um aplicativo.
* Os aplicativos que exigem que os usuários entrem têm uma opção de saída.
* Todos os fornecedores de aplicativos passam por um processo de verificação detalhada no Microsoft Partner Center. A verificação inclui verificação de email, verificação de negócios e muito mais. Para saber mais sobre a publicação de aplicativos, consulte [Como os desenvolvedores criam uma conta no Partner Center](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Guia de envio para desenvolvedores](/office/dev/store/add-in-submission-guide) e [Como os desenvolvedores publicam aplicativos](https://aka.ms/PublishToTeamsStore).
* Somente aplicativos de fornecedores verificados podem buscar permissões do Graph de usuários finais.
* Nenhum aplicativo pode baixar um arquivo executável.
* Os aplicativos são testados para não conter anúncios, promoções para outros aplicativos
* Os aplicativos são testados para funcionarem adequadamente ao trabalho sem linguagem ofensiva, bots de ataque cibernético, spam ou conteúdo fraudulento.
* Todos os links em um aplicativo são funcionais e relacionados somente à oferta do aplicativo.
* Testamos e avaliamos regularmente todos os aplicativo publicados do Teams como parte das verificações de integridade da loja de aplicativos.
* A política de privacidade e os Termos de uso que abrangem os aplicativos do Teams foram publicados pelo ISV
* Os detalhes de contato do ISV estão disponíveis na listagem da loja e em suas respectivas [páginas de Atestado do Fornecedor](/microsoft-365-app-certification/teams/teams-apps).

Além disso, a Microsoft incentiva os desenvolvedores de aplicativos a participarem do seu programa de conformidade, que é uma abordagem rigorosa de duas camadas para garantir a qualidade, a segurança e a conformidade do aplicativo. A loja do Teams tem centenas de aplicativos que vão além do cumprimento das diretrizes de validação já detalhadas e estão em conformidade com esses programas.

## <a name="publisher-verification"></a>Verificação do fornecedor

Antes que um desenvolvedor de aplicativos possa enviar seu aplicativo para a Microsoft, é necessário que o desenvolvedor seja submetido a uma verificação. Um fornecedor verifica sua identidade usando sua conta Microsoft Partner Network (MPN) e associa essa conta MPN ao registro do aplicativo. A verificação do fornecedor ajuda os administradores e usuários finais a entender a autenticidade dos desenvolvedores de aplicativos que se integram à plataforma de identidade da Microsoft. A verificação do fornecedor oferece os seguintes benefícios:

* Maior transparência e redução de riscos para os clientes - essa funcionalidade ajuda os clientes a entender quais aplicativos que estão sendo usados nas suas organizações foram publicados por desenvolvedores nos quais eles confiam.
* Identidade visual aprimorada - um selo `verified` aparece no prompt de consentimento do Microsoft Azure AD, na página Aplicativos Corporativos e em outras interfaces de usuário usadas por usuários finais e administradores.
* Adoção empresarial mais suave - os administradores podem configurar as políticas de consentimento do usuário, com o status de verificação do fornecedor como critério principal da política.

## <a name="see-also"></a>Confira também

* [Visão geral para administradores do programa de conformidade de aplicativos do Microsoft 365 ](overview-of-app-certification.md)
