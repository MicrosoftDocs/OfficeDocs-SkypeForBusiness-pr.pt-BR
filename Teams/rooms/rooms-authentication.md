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
ms.openlocfilehash: 41a65743e5da851dd8e0197e9382deaf696cd9ec
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662576"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticação em Salas do Microsoft Teams

O gerenciamento de contas para dispositivos de Salas do Microsoft Teams é tratado no nível do aplicativo. O aplicativo se conecta ao Microsoft Teams, ao Skype for Business e ao Exchange para obter recursos para a conta da sala para habilitar as experiências de chamadas e reuniões. O dispositivo é mantido em conta para permitir recursos sempre ativas, cenários de chamada (para dispositivos configurados com um Plano de Chamada) e mecanismos bloqueados personalizados implementados nesses dispositivos. Isso significa que a autenticação para esses dispositivos ocorre de uma maneira diferente de dispositivos do usuário final.  

A autenticação moderna é recomendada para todos os clientes que usam dispositivos Microsoft Teams Rooms com o Microsoft 365 ou o Office 365. Se você tiver uma implantação local do servidor Exchange [](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) ou do servidor Skype for Business, configure a autenticação moderna híbrida com o Azure Active Directory (Azure AD) para habilitar o uso da autenticação moderna.

A autenticação moderna tem suporte na versão 4.4.25.0 e posterior do Microsoft Teams Rooms.

## <a name="modern-authentication"></a>Autenticação moderna

Quando você usa a autenticação moderna com o aplicativo Salas do Microsoft Teams, a ADAL (Biblioteca de Autenticação do Active Directory) é usada para se conectar ao Microsoft Teams, Exchange e Skype for Business. Um dispositivo Microsoft Teams Rooms é um dispositivo compartilhado e executa uma reinicialização noturna para garantir o funcionamento suave e obter atualizações críticas do sistema operacional, driver, firmware ou aplicativo. O mecanismo de [](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) autenticação moderno usa o tipo de permissão de autorização de autorização de senha do proprietário do recurso no OAuth 2.0, que não requer nenhuma intervenção do usuário. Essa é uma das principais diferenças entre como a autenticação moderna funciona para contas de usuário versus contas de recursos que são usadas pelo aplicativo Salas do Microsoft Teams. Por isso, as contas de recurso salas do Microsoft Teams não devem ser configuradas para usar a autenticação multifafatória (MFA), a autenticação de cartão inteligente ou a autenticação baseada em certificado do cliente (que estão todas disponíveis para usuários finais).

A outra principal diferença entre como a autenticação moderna funciona em dispositivos de Salas do Microsoft Teams e dispositivos de usuário final é que você não pode usar uma conta de recurso para aplicar políticas de acesso condicional no nível do dispositivo no Azure Active Directory e no Endpoint Manager, pois as informações do dispositivo não são passadas ao usar esse tipo de concessão. Em vez disso, você pode registrar um dispositivo no Microsoft Endpoint Manager e aplicar políticas de conformidade usando as diretrizes fornecidas no Gerenciamento de Salas de Reunião do [Teams com o Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Habilitar a autenticação moderna em um dispositivo salas do Microsoft Teams

Para que as Salas do Microsoft Teams usem a autenticação moderna com o Skype for Business e o Exchange, habilita a configuração do lado do cliente para autenticação moderna no dispositivo Salas do Microsoft Teams. Você pode fazer isso nas configurações do dispositivo ou no arquivo de configuração XML.

> [!NOTE]
> Antes de habilitar a configuração do lado do cliente para autenticação moderna, certifique-se de que seu ambiente está definido corretamente para usar a autenticação moderna.

### <a name="using-device-settings"></a>Usando as configurações do dispositivo

1. No dispositivo Salas de Equipe da Microsoft, vá **para Mais** (**...**).
    
2. Selecione **Configurações e** insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá para **a guia Conta,** a **opção** Autenticação Moderna e selecione Salvar **e Sair.**

### <a name="using-the-xml-config-file"></a>Usando o arquivo de configuração XML

No arquivo SkypeSettings.xml, de definir o elemento XML de autenticação moderna como **True,** da seguinte forma.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar a configuração, consulte Gerenciar remotamente as configurações de um console de [Salas do Microsoft Teams com um arquivo de configuração XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar seu ambiente para autenticação moderna

Antes de começar, certifique-se de compreender os modelos de identidade a ser usado com o Office 365 e o Azure AD. Você pode encontrar mais informações nos modelos de identidade do [Office 365](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) e no Azure Active Directory e na sincronização de identidade híbrida e diretório do [Microsoft 365 ou do Office 365.](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar a autenticação moderna no Microsoft 365 ou no Office 365

Para ativar a autenticação moderna para o Exchange Online, consulte [Habilitar autenticação moderna no Exchange Online.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Se você usa o Skype for Business Online, também deve certificar-se de que a autenticação moderna está responsabilidade do Skype for Business Online. Para saber mais, confira [o Skype for Business Online: Habilitar seu locatário para autenticação moderna.](https://aka.ms/SkypeModernAuth)

Recomendamos que você não remova políticas básicas de autenticação do Exchange Online ou desabilite a autenticação básica para seu locatário até ter validado que os dispositivos de Salas do Microsoft Teams podem entrar com êxito com o Exchange Online, o Teams e o Skype for Business Online.

Para saber mais sobre como desabilitar a autenticação básica no Exchange Online, consulte Desabilitar a autenticação [básica no Exchange Online.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Autenticação moderna híbrida

Para garantir a autenticação bem-sucedida para o servidor Exchange local e/ou o servidor Skype for Business, verifique se a conta de recurso usada com salas do Microsoft Teams está configurada para obter autorização do Azure AD. 

Os fluxos de autenticação de Salas do Teams variam dependendo da configuração de autenticação. Para clientes que usam um domínio gerenciado, as Salas do Teams usam Credenciais de Senha do Proprietário do Recurso [OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) com o Azure Active Directory. No entanto, para clientes que usam um domínio federado, [OAuth 2.0 SAML Bearer Assertion Flow](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion) é usado.

> [!NOTE]
> Seu provedor de identidade pode precisar de configurações ou configurações específicas para integração com o Azure Active Directory ou o Office 365. Entre em contato com seu provedor de identidade se precisar de ajuda para configurar a autenticação com salas do Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Pré-requisitos específicos das Salas do Microsoft Teams

Os pré-requisitos para habilitar a autenticação moderna em sua topologia híbrida são abordados na visão geral de autenticação moderna híbrida e [pré-requisitos para usá-la](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)com servidores locais do Skype for Business e do Exchange. Todos os pré-requisitos discutidos no artigo são aplicados.

No entanto, como as Salas do Microsoft Teams usam a autorização de credenciais de proprietário de recursos e as APIs REST subjacentes para autenticação moderna, as seguintes diferenças são importantes para se ter em conta que são [específicas](https://tools.ietf.org/html/rfc6749#section-1.3.3) das Salas do Microsoft Teams.

- Você deve ter o Exchange Server 2016 CU8 ou posterior, ou o Exchange Server 2019 CU1 ou posterior.
- Você deve ter o Skype for Business Server 2015 CU5 ou posterior, ou o Skype for Business Server 2019 ou posterior.
- A MFA não tem suporte independentemente da topologia que você tem.
- As Salas do Microsoft Teams não são suportadas por incompatibilidade de SIP e UPN. Você deve criar uma conta do Microsoft Teams Rooms com o mesmo UPN e SIP para que ela funcione.
- Se você usar um provedor de autenticação de terceiros com suporte do Azure AD, ele deverá dar suporte a um fluxo de autenticação ativa por meio da WS-Trust.
- Não use políticas de acesso condicional no nível do dispositivo para uma conta de recurso configurada com o aplicativo. Isso resultará em falhas de logona. Em vez disso, registrar um dispositivo no Microsoft Intune e aplicar políticas de conformidade usando as diretrizes publicadas no Gerenciamento de Salas de Reunião do [Teams com o Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurar o Exchange Server

Para habilitar a autenticação moderna híbrida no Exchange Server, consulte Como configurar o [Exchange Server local para usar a autenticação moderna híbrida.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurar o Skype for Business Server

Para habilitar a autenticação moderna híbrida com o Skype for Business Server, consulte Como configurar o Skype for Business local para [usar a autenticação moderna híbrida.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Remover ou desabilitar o Skype for Business e o Exchange

Se sua configuração não permitir a autenticação moderna híbrida ou se você precisar remover ou desabilitar a autenticação moderna híbrida do Exchange ou do Skype for Business, consulte Remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do [Exchange.](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Acesso condicional do Azure AD

Você pode configurar uma conta de recurso usada com salas do Microsoft Teams para acesso baseado em IP/local. Para saber mais, consulte [Acesso Condicional: Bloquear o acesso por local.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Nenhuma outra política de acesso condicional é suportada. Para obter mais informações sobre conformidade com o dispositivo, consulte [Gerenciar Salas de Reunião do Teams com o Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)  
