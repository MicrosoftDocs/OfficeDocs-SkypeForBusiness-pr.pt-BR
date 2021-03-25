---
title: Autenticação em Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Saiba como configurar a autenticação moderna para salas do Microsoft Teams
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117479"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticação em Salas do Microsoft Teams

O gerenciamento de contas para dispositivos de Salas do Microsoft Teams é manipulado no nível do aplicativo. O aplicativo se conecta ao Microsoft Teams, Skype for Business e Exchange para obter recursos para a conta de sala para habilitar experiências de chamadas e reuniões. O dispositivo é mantido em conta agnostic para permitir recursos always-on, cenários de chamada (para dispositivos configurados com um Plano de Chamada) e mecanismos de bloqueio personalizados implementados nesses dispositivos. Isso significa que a autenticação para esses dispositivos ocorre de uma maneira diferente dos dispositivos do usuário final.  

A autenticação moderna é recomendada para todos os clientes que usam dispositivos do Microsoft Teams Rooms com o Microsoft 365 ou o Office 365. Se você tiver uma implantação local do servidor Exchange ou do Skype for Business, [configure](/office365/enterprise/hybrid-modern-auth-overview) a autenticação moderna híbrida com o Azure Active Directory (Azure AD) para habilitar o uso da autenticação moderna.

A autenticação moderna é suportada nas Salas do Microsoft Teams versão 4.4.25.0 e posteriores.

## <a name="modern-authentication"></a>Autenticação moderna

Quando você usa autenticação moderna com o aplicativo salas do Microsoft Teams, a Biblioteca de Autenticação do Active Directory (ADAL) é usada para se conectar ao Microsoft Teams, Exchange e Skype for Business. Um dispositivo salas do Microsoft Teams é um dispositivo compartilhado e executa uma reinicialização noturna para garantir o funcionamento suave e obter atualizações críticas do sistema operacional, driver, firmware ou aplicativo. O mecanismo de [](/azure/active-directory/develop/v2-oauth-ropc) autenticação moderno usa o tipo de concessão de autorização de credenciais de senha do proprietário do recurso no OAuth 2.0, que não exige nenhuma intervenção do usuário. Essa é uma das principais diferenças entre como a autenticação moderna funciona para contas de usuário e contas de recurso que são usadas pelo aplicativo Salas do Microsoft Teams. Devido a isso, as contas de recursos do Microsoft Teams Rooms não devem ser configuradas para usar a autenticação multifa factor (MFA), autenticação de cartão inteligente ou autenticação baseada em certificado do cliente (que estão todas disponíveis para usuários finais).

A outra diferença importante entre como funciona a autenticação moderna em dispositivos microsoft Teams Rooms e dispositivos de usuário final é que você não pode usar uma conta de recurso para aplicar políticas de acesso condicional no nível do dispositivo no Azure Active Directory e no Endpoint Manager como informações de dispositivo não são passadas ao usar esse tipo de concessão. Em vez disso, você pode registrar um dispositivo no Microsoft Endpoint Manager e aplicar políticas de conformidade usando as diretrizes fornecidas em [Managing Teams Meeting Rooms with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Habilitar a autenticação moderna em um dispositivo salas do Microsoft Teams

Para que as Salas do Microsoft Teams usem autenticação moderna com o Skype for Business e o Exchange, habilita a configuração do lado do cliente para autenticação moderna no dispositivo salas do Microsoft Teams. Você pode fazer isso nas configurações do dispositivo ou no arquivo de configuração XML.

> [!NOTE]
> Antes de habilitar a configuração do lado do cliente para autenticação moderna, certifique-se de que seu ambiente está definido corretamente para usar a autenticação moderna.

### <a name="using-device-settings"></a>Usando configurações de dispositivo

1. No dispositivo Salas de Equipe da Microsoft, vá para **Mais** (**...**).
    
2. Selecione **Configurações** e insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá para a **guia Conta,** acione **Autenticação** Moderna e selecione **Salvar e sair**.

### <a name="using-the-xml-config-file"></a>Usando o arquivo de configuração XML

No arquivo SkypeSettings.xml, de definir o elemento XML de autenticação moderna como **True**, da seguinte forma.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar a configuração, consulte [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar seu ambiente para autenticação moderna

Antes de começar, entenda os modelos de identidade a ser usado com o Office 365 e o Azure AD. Você pode encontrar mais informações nos modelos de identidade do [Office 365](/Office365/Enterprise/about-office-365-identity) e no Azure Active Directory e na sincronização de identidade híbrida e diretório para [o Microsoft 365 ou Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar autenticação moderna no Microsoft 365 ou Office 365

Para ativar a autenticação moderna para o Exchange Online, consulte [Enable modern authentication in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Se você usar o Skype for Business Online, certifique-se de que a autenticação moderna está 100% 100% 100%. Para saber mais, confira [Skype for Business Online: Habilitar seu locatário para autenticação moderna.](https://aka.ms/SkypeModernAuth)

Recomendamos que você não remova políticas básicas de autenticação para o Exchange Online ou desabilite a autenticação básica para seu locatário até que você tenha validado que os dispositivos de Salas do Microsoft Teams podem entrar com êxito com o Exchange Online, o Teams e o Skype for Business Online.

Para obter mais informações sobre como desabilitar a autenticação básica no Exchange Online, consulte [Disable Basic authentication in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticação moderna híbrida

Para garantir a autenticação bem-sucedida para seu servidor Exchange local e/ou servidor skype for Business, você deve garantir que a conta de recurso usada com salas do Microsoft Teams está configurada para obter autorização do Azure AD. 

Os fluxos de autenticação de Salas do Teams variam dependendo da configuração de autenticação. Para clientes que usam um domínio gerenciado, as Salas do Teams usam Credenciais de Senha do Proprietário de Recursos [do OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) com o Azure Active Directory. No entanto, para clientes que usam um domínio federado, o Fluxo de Afirmação do Portador [do SAML OAuth 2.0](/azure/active-directory/develop/v2-saml-bearer-assertion) é usado.

> [!NOTE]
> Seu provedor de identidade pode precisar de configurações ou configurações específicas para integração com o Azure Active Directory ou o Office 365. Entre em contato com seu provedor de identidade se precisar de ajuda para configurar a autenticação com salas do Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Pré-requisitos específicos para salas do Microsoft Teams

Os pré-requisitos para habilitar a autenticação moderna em sua topologia híbrida são abordados em Visão geral de autenticação moderna híbrida e [pré-requisitos para usá-la](/office365/enterprise/hybrid-modern-auth-overview)com servidores locais do Skype for Business e exchange. Todos os pré-requisitos discutidos no artigo se aplicam.

No entanto, como as Salas do Microsoft Teams usam a autorização de credenciais de senha do proprietário do recurso e as APIs REST subjacentes para autenticação moderna, as seguintes são diferenças importantes a serem cientes de que são [específicas](https://tools.ietf.org/html/rfc6749#section-1.3.3) das Salas do Microsoft Teams.

- Você deve ter Exchange Server 2016 CU8 ou posterior, ou Exchange Server 2019 CU1 ou posterior.
- Você deve ter o Skype for Business Server 2015 CU5 ou posterior, ou o Skype for Business Server 2019 ou posterior.
- O MFA não é suportado independentemente da topologia que você tem.
- As Salas do Microsoft Teams não suportam a incompatibilidade SIP e UPN. Você deve criar uma conta do Microsoft Teams Rooms com o mesmo UPN e SIP para que ela funcione.
- Se você usar um provedor de autenticação de terceiros com suporte do Azure AD, ele deverá dar suporte a um fluxo de autenticação ativo por meio do WS-Trust.
- Não use políticas de acesso condicional no nível do dispositivo para uma conta de recurso configurada com o aplicativo. Isso resultará em falhas de login. Em vez disso, inscreva um dispositivo no Microsoft Intune e aplique políticas de conformidade usando as diretrizes publicadas em [Managing Teams Meeting Rooms with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

### <a name="configure-exchange-server"></a>Configurar Exchange Server

Para habilitar a autenticação moderna híbrida Exchange Server, consulte [How to configure Exchange Server local to use hybrid modern authentication](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurar o Skype for Business Server

Para habilitar a autenticação moderna híbrida com o Skype for Business Server, consulte Como configurar o Skype for Business local para [usar a autenticação moderna híbrida.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Remover ou desabilitar o Skype for Business e o Exchange

Se sua instalação não permitir a autenticação moderna híbrida ou você precisar remover ou desabilitar a autenticação moderna híbrida para Exchange ou Skype for Business, consulte Removendo ou [desabilitando](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)a autenticação moderna híbrida do Skype for Business e do Exchange .

### <a name="azure-ad-conditional-access"></a>Acesso condicional do Azure AD

Você pode configurar uma conta de recurso usada com salas do Microsoft Teams para acesso baseado em IP/local. Para saber mais, confira [Acesso Condicional: Bloquear o acesso por local](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Nenhuma outra política de acesso condicional é suportada. Para obter mais informações sobre a conformidade do dispositivo, consulte [Managing Teams Meeting Rooms with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).