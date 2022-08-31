---
title: Experiências Conectadas Opcionais do Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: ''
ms.localizationpriority: high
search.appverid: MET150
description: Este artigo descreve as experiências conectadas opcionais que você verá no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03c23ccc1e9d24733f083c3e1d780b38138d366e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396262"
---
# <a name="overview-of-optional-connected-experiences-in-microsoft-teams"></a>Visão geral das experiências conectadas opcionais no Microsoft Teams

Se você tiver uma conta corporativa ou de estudante, o administrador da sua organização poderá fornecer a você a capacidade de usar um ou mais serviços baseados em nuvem (também chamados de **"experiências conectadas opcionais"**) ao usar o Microsoft Teams, como GIPHY e/ou o serviço de Prévia de URL. Esses serviços baseados em nuvem são opcionais. O uso deles é uma escolha sua. Eles são oferecidos a você em termos que diferem dos Termos de Serviço [Online da Microsoft](https://www.microsoft.com/licensing/product-licensing/products), conforme descrito separadamente para cada serviço opcional. Este artigo lista os serviços do Teams com suporte à nuvem.

Se o administrador tiver dado a você a capacidade de usar experiências conectadas opcionais no Teams, você poderá acessar **Configurações** > **Privacidade** no Teams e escolher se deseja usar experiências conectadas opcionais.

> [!NOTE]
> Se for um administrador, você poderá dar ou restringir a capacidade dos usuários de usar experiências conectadas opcionais. Você pode fazer isso usando o [serviço de política de nuvem do Office](/deployoffice/overview-office-cloud-policy-service) e configurando o *Permitir o uso de experiências conectadas opcionais adicionais na configuração de política do Office*. Essa é a mesma configuração de política que controla se as experiências conectadas opcionais estão disponíveis para os usuários nos aplicativos do Office (como Word, Excel e PowerPoint) que vêm com os o Microsoft 365 Apps para Grandes Empresas.

## <a name="giphy"></a>GIPHY

O GIPHY é um serviço de nuvem que permite que você use GIFs em conversas do Teams. Se você estiver na Pesquisa **de GIF** > **do** **Teams** > , os termos de pesquisa serão enviados para o GIPHY. Essas experiências, se permitidas pelo seu administrador e depois que você optar por usá-las, estarão sujeitas à [Política de Privacidade do GIPHY](https://support.giphy.com/hc/articles/360032872931-GIPHY-Privacy-Policy) e aos [Termos de Serviço](https://support.giphy.com/hc/articles/360020027752-GIPHY-User-Terms-of-Service).

:::image type="content" source="media/giphy-menu.png" alt-text="Esse é um menu que mostra o botão de seleção do Giphy e a caixa de texto para a digitação de informações para recuperar uma imagem ou imagens do Giphy.":::

## <a name="url-preview-service"></a>Serviço de Visualização de URL

O serviço de visualização de URL gera, automaticamente, um trecho de visualização e é anexado a um trecho na URL quando um usuário envia uma cadeia de caracteres de URL. Esse serviço fará uma solicitação para a URL do serviço, conforme o usuário está digitando a mensagem. Se a URL do serviço não tiver dados schema.org, ela enviará uma solicitação à pesquisa do Bing para obter os dados necessários para gerar o snippet de visualização. As experiências que dependem do Bing são licenciadas para você nos termos do [Contrato de Serviços Da Microsoft](https://www.microsoft.com/servicesagreement) e cobertas pela [política de privacidade](https://privacy.microsoft.com/privacystatement). Todas as URLs fornecidas ao Microsoft Teams ao usar esses serviços podem ser enviadas ao Microsoft Bing. Eles não estão vinculados a você pela organização do Bing.

:::image type="content" source="media/url-preview.png" alt-text="Tela mostrando um exemplo de uma visualização de URL para a página inicial da Microsoft em uma caixa de texto.":::

## <a name="teams-apps-link-previews"></a>Visualizações de link de aplicativos do Teams

O serviço de visualizações de link de aplicativo do Teams gera um snippet de visualização do cartão adaptável do aplicativo e o anexa na URL quando um usuário envia uma cadeia de caracteres de URL que é mapeada para o aplicativo na loja do Teams. Esse serviço fará uma solicitação para a URL do serviço, conforme o usuário está digitando a mensagem.

## <a name="teams-device-store-checkout"></a>Check-out do repositório de dispositivos do Teams  

O repositório de dispositivos do Teams está no centro de administração do Teams e permite a descoberta e a compra de dispositivos certificados do Teams. Para habilitar o check-out, o repositório de dispositivos do Teams compartilha informações básicas do usuário e da empresa, incluindo endereço de email do usuário, GUIDs de usuário e GUIDs de locatário, com UnifiedCommunications.com. Essa experiência, se permitida pelo uso de experiências conectadas opcionais adicionais na configuração de política do **Office** , está sujeita aos termos de serviço e à política de privacidade do UnifiedCommunications.com.

:::image type="content" source="media/teams-device-store-buttons.png" alt-text="Uma captura de tela de uma parte da página de armazenamento de dispositivos do Teams com opções de Checkout fornecidas pelo UnifiedCommunications.com, uma empresa de terceiros que permite a compra de dispositivos no Centro de administração do Teams.":::

Para saber mais sobre a loja de dispositivos do Teams, confira: [Comprar dispositivos na loja de dispositivos do Teams](devices/device-store.md)

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral de controles de política para o Teams](policy-control-overview.md)
- [Privacidade e Microsoft Teams](teams-privacy.md)
- [Visão geral das experiências conectadas opcionais no Office](/deployoffice/privacy/optional-connected-experiences)
- [Dados de serviço necessários para o Office](/deployoffice/privacy/required-service-data)
- [Configurações de Privacidade da Conta](https://support.microsoft.com/office/3e7bc183-bf52-4fd0-8e6b-78978f7f121b)
