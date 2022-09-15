---
title: Autenticação no Salas do Microsoft Teams no Windows
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
description: Saiba como configurar a autenticação moderna para Salas do Microsoft Teams no Windows
ms.openlocfilehash: 23e08b48c5d161caf8091068abc4c9cda0061122
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706428"
---
# <a name="authentication-in-microsoft-teams-rooms-on-windows"></a>Autenticação no Salas do Microsoft Teams no Windows

O gerenciamento de conta Salas do Microsoft Teams é tratado no nível do aplicativo. O aplicativo se conecta ao Microsoft Teams, ao Skype for Business e ao Exchange para obter recursos para a conta de recurso para habilitar experiências de chamada e reunião. Salas do Teams usa uma conta de recurso dedicada para permitir recursos sempre ativados, cenários de chamada (para dispositivos configurados com um plano de chamada) e mecanismos de bloqueio personalizados. Isso significa que a autenticação Salas do Teams ocorre de uma maneira diferente para dispositivos do usuário final.  

A autenticação moderna é recomendada para todos os clientes que usam Salas do Microsoft Teams com o Microsoft 365 ou Office 365. Se você tiver uma implantação local do servidor Exchange ou do Skype for Business, configure a autenticação moderna híbrida com o Azure Active Directory (Azure AD) para habilitar o uso da autenticação moderna.[](/office365/enterprise/hybrid-modern-auth-overview)

A autenticação moderna tem suporte Salas do Microsoft Teams versão 4.4.25.0 e posterior.

## <a name="modern-authentication"></a>Autenticação moderna

Quando você usa a autenticação moderna com o aplicativo Salas do Microsoft Teams, a ADAL (Biblioteca de Autenticação do Active Directory) é usada para se conectar ao Microsoft Teams, Exchange e Skype for Business. O mecanismo de autenticação moderno [](/azure/active-directory/develop/v2-oauth-ropc) usa o tipo de concessão de autorização de credenciais de senha do proprietário do recurso no OAuth 2.0, que não requer nenhuma intervenção do usuário. Essa é uma das principais diferenças entre como a autenticação moderna funciona para contas de usuário versus contas de recursos que são usadas pelo Salas do Microsoft Teams. Por isso, Salas do Microsoft Teams contas de recursos não devem ser configuradas para usar a MFA (autenticação multifator), a autenticação de cartão inteligente ou a autenticação baseada em certificado do cliente (que estão todas disponíveis para usuários finais).

A outra diferença importante entre como a autenticação moderna funciona em dispositivos Salas do Microsoft Teams e do usuário final é que você não pode usar uma conta de recurso para aplicar políticas de acesso condicional no nível do dispositivo no Azure Active Directory e no Endpoint Manager, pois as informações do dispositivo não são passadas ao usar esse tipo de concessão. Em vez disso, você pode registrar um dispositivo no Microsoft Endpoint Manager e aplicar políticas de conformidade. Consulte [Acesso Condicional e conformidade Intune para Salas do Microsoft Teams](conditional-access-and-compliance-for-devices.md) para obter mais informações.

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Habilitar a autenticação moderna Salas do Microsoft Teams

Para Salas do Microsoft Teams a autenticação moderna com o Skype for Business e o Exchange, habilite a configuração do lado do cliente para autenticação moderna no Salas do Microsoft Teams. Você pode fazer isso nas configurações do dispositivo ou no arquivo de configuração XML.

> [!NOTE]
> Antes de habilitar a configuração do lado do cliente para autenticação moderna, verifique se o ambiente está configurado corretamente para usar a autenticação moderna.

### <a name="using-device-settings"></a>Usando configurações de dispositivo

1. No Salas do Microsoft Teams, vá para **Mais** (**...**).
    
2. Selecione **Configurações e** insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá para a **guia Conta** , ative a **Autenticação Moderna** e, em seguida, **selecione Salvar e sair**.

### <a name="using-the-xml-config-file"></a>Usando o arquivo de configuração XML

No arquivo SkypeSettings.xml, defina o elemento XML de autenticação moderna como **True**, da seguinte maneira.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar a configuração, consulte [Gerenciar um Salas do Microsoft Teams console remotamente com um arquivo de configuração XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar seu ambiente para autenticação moderna

Antes de começar, certifique-se de entender os modelos de identidade a serem Office 365 e Azure AD. Você pode encontrar mais informações em Office 365 de identidade e [no Azure Active Directory](/Office365/Enterprise/about-office-365-identity) e na sincronização de diretório e identidade híbrida para [o Microsoft 365 ou Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar a autenticação moderna no Microsoft 365 ou Office 365

Para ativar a autenticação moderna para Exchange Online, consulte [Habilitar a autenticação moderna Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

Recomendamos que você não remova políticas básicas de autenticação para o Exchange Online ou desabilite a autenticação básica para seu locatário até que você valide que os dispositivos Salas do Microsoft Teams podem entrar com êxito com o Exchange Online e o Teams.

Para obter mais informações sobre como desabilitar a autenticação básica no Exchange Online, consulte [Desabilitar a autenticação básica Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticação moderna híbrida

Para garantir a autenticação bem-sucedida para o servidor Exchange local e/ou servidor Skype for Business, verifique se a conta de recurso usada com o Salas do Microsoft Teams está configurada para obter autorização do Azure AD.

Salas do Teams fluxos de autenticação variam dependendo da configuração de autenticação. Para clientes que usam um domínio gerenciado, o Salas do Teams usa credenciais de senha de proprietário de recurso [do OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) com o Azure Active Directory. No entanto, para clientes que usam um domínio federado, o Fluxo de Declaração [do Portador SAML do OAuth 2.0](/azure/active-directory/develop/v2-saml-bearer-assertion) é usado.

> [!NOTE]
> Seu provedor de identidade pode precisar de configurações ou configurações específicas para integração com o Azure Active Directory ou Office 365. Entre em contato com seu provedor de identidade se precisar de ajuda para configurar a autenticação com Salas do Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Pré-requisitos específicos para Salas do Microsoft Teams

Os pré-requisitos para habilitar a autenticação moderna em sua topologia híbrida são abordados na visão geral da autenticação moderna híbrida e nos [pré-requisitos para usá-la com servidores locais Skype for Business e Exchange](/office365/enterprise/hybrid-modern-auth-overview). Todos os pré-requisitos discutidos no artigo se aplicam.

No entanto, como o Salas do Microsoft Teams usa a autorização de credenciais de senha do proprietário do recurso e as APIs REST subjacentes para autenticação moderna, a seguir estão diferenças importantes a serem [consideradas específicas](https://tools.ietf.org/html/rfc6749#section-1.3.3) para Salas do Microsoft Teams.

- Você deve ter Exchange Server 2016 CU8 ou posterior ou Exchange Server 2019 CU1 ou posterior.
- Você deve ter Skype for Business Server 2015 CU5 ou posterior ou Skype for Business Server 2019 ou posterior.
- Não há suporte para MFA, independentemente da topologia que você tem.
- Salas do Microsoft Teams não dá suporte à incompatibilidade de SIP e UPN. Você deve criar uma Salas do Microsoft Teams com o mesmo UPN e SIP para que ela funcione.
- Se você usar um provedor de autenticação de terceiros com suporte do Azure AD, ele deverá dar suporte a um fluxo de autenticação ativo por meio do WS-Trust.
- Não use políticas de acesso condicional no nível do dispositivo para uma conta de recurso configurada com o aplicativo. Isso resultará em falhas de entrada. Em vez disso, registre um dispositivo no Microsoft Intune e aplique políticas de conformidade. Consulte [Acesso Condicional e conformidade Intune para Salas do Microsoft Teams](conditional-access-and-compliance-for-devices.md) para obter mais informações.

### <a name="configure-exchange-server"></a>Configurar Exchange Server

Para habilitar a autenticação moderna híbrida no Exchange Server, consulte Como configurar Exchange Server [local para usar a autenticação moderna híbrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurar Skype for Business Server

Para habilitar a autenticação moderna híbrida com Skype for Business Server, consulte Como configurar Skype for Business [local para usar a autenticação moderna híbrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Remover ou desabilitar o Skype for Business e o Exchange

Se sua configuração não permitir a autenticação moderna híbrida ou se você precisar remover ou desabilitar a autenticação moderna híbrida para o Exchange ou o Skype for Business, consulte Remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do [Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Azure AD acesso condicional

Você pode configurar uma conta de recurso usada com Salas do Microsoft Teams para acesso baseado em IP/localização. Para saber mais, confira [Acesso Condicional: bloquear o acesso por local](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Para obter mais informações sobre a conformidade do dispositivo, consulte Acesso Condicional e políticas de conformidade Intune [suporte para Salas do Microsoft Teams](supported-ca-and-compliance-policies.md).
