---
title: Autenticação no Salas do Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Saiba como configurar a autenticação moderna para Salas do Microsoft Teams
ms.openlocfilehash: de1487cce0c8a79d2a6c672f5cb729e247966c50
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106296"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticação no Salas do Microsoft Teams

O gerenciamento de conta Salas do Microsoft Teams é tratado no nível do aplicativo. O aplicativo se conecta Microsoft Teams, Skype for Business e Exchange para obter recursos para a conta de recurso para habilitar experiências de chamada e reunião. Salas do Teams usa uma conta de recurso dedicada para permitir recursos sempre ativados, cenários de chamada (para dispositivos configurados com um plano de chamada) e mecanismos de bloqueio personalizados. Isso significa que a autenticação Salas do Teams ocorre de uma maneira diferente para dispositivos do usuário final.  

A autenticação moderna é recomendada para todos os clientes que usam Salas do Microsoft Teams com Microsoft 365 ou Office 365. Se você tiver uma implantação local do servidor Exchange ou do Skype for Business, configure a autenticação moderna híbrida com o Azure Active Directory (Azure AD) para habilitar o uso da autenticação moderna.[](/office365/enterprise/hybrid-modern-auth-overview)

A autenticação moderna tem suporte Salas do Microsoft Teams versão 4.4.25.0 e posterior.

## <a name="modern-authentication"></a>Autenticação moderna

Quando você usa a autenticação moderna com o aplicativo Salas do Microsoft Teams, a ADAL (Biblioteca de Autenticação do Active Directory) é usada para se conectar ao Microsoft Teams, Exchange e Skype for Business. O mecanismo de autenticação moderno [](/azure/active-directory/develop/v2-oauth-ropc) usa o tipo de concessão de autorização de credenciais de senha do proprietário do recurso no OAuth 2.0, que não requer nenhuma intervenção do usuário. Essa é uma das principais diferenças entre como a autenticação moderna funciona para contas de usuário versus contas de recursos que são usadas pelo Salas do Microsoft Teams. Por isso, Salas do Microsoft Teams contas de recursos não devem ser configuradas para usar a MFA (autenticação multifator), a autenticação de cartão inteligente ou a autenticação baseada em certificado do cliente (que estão todas disponíveis para usuários finais).

A outra diferença importante entre como a autenticação moderna funciona em dispositivos Salas do Microsoft Teams e do usuário final é que você não pode usar uma conta de recurso para aplicar políticas de acesso condicional no nível do dispositivo no Azure Active Directory e no Endpoint Manager, pois as informações do dispositivo não são passadas ao usar esse tipo de concessão. Em vez disso, você pode registrar um dispositivo no Microsoft Endpoint Manager e aplicar políticas de conformidade. Consulte [Acesso Condicional e conformidade Intune para Salas do Microsoft Teams](conditional-access-and-compliance-for-devices.md) para obter mais informações.

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Habilitar a autenticação moderna Salas do Microsoft Teams

Para Salas do Microsoft Teams a autenticação moderna com Skype for Business e Exchange, habilite a configuração do lado do cliente para autenticação moderna no Salas do Microsoft Teams. Você pode fazer isso nas configurações do dispositivo ou no arquivo de configuração XML.

> [!NOTE]
> Antes de habilitar a configuração do lado do cliente para autenticação moderna, verifique se o ambiente está configurado corretamente para usar a autenticação moderna.

### <a name="using-device-settings"></a>Usando configurações de dispositivo

1. No Salas do Microsoft Teams, vá para **Mais** (**...**).
    
2. Selecione **Configurações** e insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá para a **guia Conta** , ative a **Autenticação Moderna** e, em seguida, **selecione Salvar e sair**.

### <a name="using-the-xml-config-file"></a>Usando o arquivo de configuração XML

No arquivo SkypeSettings.xml, defina o elemento XML de autenticação moderna como **True**, da seguinte maneira.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar a configuração, consulte [Gerenciar um Salas do Microsoft Teams console remotamente com um arquivo de configuração XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar seu ambiente para autenticação moderna

Antes de começar, entenda os modelos de identidade a serem usado com o Office 365 e o Azure AD. Você pode encontrar mais informações [Office 365](/Office365/Enterprise/about-office-365-identity) modelos de identidade e Azure Active Directory e na sincronização de diretório e identidade híbrida para Microsoft 365 [ou Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar a autenticação moderna Microsoft 365 ou Office 365

Para ativar a autenticação moderna para Exchange Online, consulte [Habilitar a autenticação moderna Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

Recomendamos que você não remova políticas básicas de autenticação para o Exchange Online ou desabilite a autenticação básica para seu locatário até que você valide que os dispositivos Salas do Microsoft Teams podem entrar com êxito com Exchange Online e Teams.

Para obter mais informações sobre como desabilitar a autenticação básica no Exchange Online, consulte [Desabilitar a autenticação básica Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticação moderna híbrida

Para garantir a autenticação bem-sucedida para seu servidor Exchange local e/ou servidor Skype for Business, verifique se a conta de recurso usada com o Salas do Microsoft Teams está configurada para obter autorização do Azure AD.

Salas do Teams fluxos de autenticação variam dependendo da configuração de autenticação. Para clientes que usam um domínio gerenciado, o Salas do Teams usa credenciais de senha do proprietário do recurso [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) com Azure Active Directory. No entanto, para clientes que usam um domínio federado, a declaração de portador [SAML do OAuth 2.0 Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) é usada.

> [!NOTE]
> Seu provedor de identidade pode precisar de configurações ou configurações específicas para integração com Azure Active Directory ou Office 365. Entre em contato com seu provedor de identidade se precisar de ajuda para configurar a autenticação com Salas do Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Pré-requisitos específicos para Salas do Microsoft Teams

Os pré-requisitos para habilitar a autenticação moderna em sua topologia híbrida são abordados na visão geral da autenticação moderna híbrida e nos [pré-requisitos para usá-la](/office365/enterprise/hybrid-modern-auth-overview) com servidores Skype for Business e Exchange locais. Todos os pré-requisitos discutidos no artigo se aplicam.

No entanto, como o Salas do Microsoft Teams usa a autorização de credenciais de senha do proprietário do recurso e as APIs REST subjacentes para autenticação moderna, a seguir estão diferenças importantes a serem [consideradas específicas](https://tools.ietf.org/html/rfc6749#section-1.3.3) para Salas do Microsoft Teams.

- Você deve ter Exchange Server 2016 CU8 ou posterior ou Exchange Server 2019 CU1 ou posterior.
- Você deve ter Skype for Business Server 2015 CU5 ou posterior ou Skype for Business Server 2019 ou posterior.
- Não há suporte para MFA, independentemente da topologia que você tem.
- Salas do Microsoft Teams não dá suporte à incompatibilidade de SIP e UPN. Você deve criar uma Salas do Microsoft Teams com o mesmo UPN e SIP para que ela funcione.
- Se você usar um provedor de autenticação de terceiros compatível com o Azure AD, ele deverá dar suporte a um fluxo de autenticação ativo por meio do WS-Trust.
- Não use políticas de acesso condicional no nível do dispositivo para uma conta de recurso configurada com o aplicativo. Isso resultará em falhas de entrada. Em vez disso, registre um dispositivo no Microsoft Intune e aplique políticas de conformidade. Consulte [Acesso Condicional e conformidade Intune para Salas do Microsoft Teams](conditional-access-and-compliance-for-devices.md) para obter mais informações.

### <a name="configure-exchange-server"></a>Configurar Exchange Server

Para habilitar a autenticação moderna híbrida no Exchange Server, consulte Como configurar Exchange Server [local para usar a autenticação moderna híbrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurar Skype for Business Server

Para habilitar a autenticação moderna híbrida com Skype for Business Server, consulte Como configurar Skype for Business [local para usar a autenticação moderna híbrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Remover ou desabilitar Skype for Business e Exchange

Se sua configuração não permitir a autenticação moderna híbrida ou se você precisar remover ou desabilitar a autenticação moderna híbrida para Exchange ou Skype for Business, consulte Remover ou desabilitar a autenticação moderna híbrida do [Skype for Business e Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Acesso condicional do Azure AD

Você pode configurar uma conta de recurso usada com Salas do Microsoft Teams para acesso baseado em IP/localização. Para saber mais, confira [Acesso Condicional: bloquear o acesso por local](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Nenhuma outra política de acesso condicional é compatível. Para obter mais informações sobre a conformidade do dispositivo, consulte Acesso Condicional e políticas de conformidade Intune [suporte para Salas do Microsoft Teams](supported-ca-and-compliance-policies.md).
