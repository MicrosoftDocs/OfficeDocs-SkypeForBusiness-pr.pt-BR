---
title: Autenticação em salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: bef547ab0b9ade2edc433ec64bb1ef61eee4c040
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160105"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticação em salas do Microsoft Teams

O gerenciamento de contas para dispositivos de salas do Microsoft Teams é manipulado no nível do aplicativo. O aplicativo se conecta ao Microsoft Teams, ao Skype for Business e ao Exchange para obter recursos para a conta da sala para habilitar as experiências de chamada e reunião. O dispositivo é mantido na conta para permitir recursos sempre ativados, cenários de chamada (para dispositivos configurados com um plano de chamada) e mecanismos de bloqueio personalizados implementados nesses dispositivos. Isso significa que a autenticação para esses dispositivos ocorre de uma maneira diferente do que os dispositivos do usuário final.  

A autenticação moderna é recomendada para todos os clientes que usam dispositivos de salas do Microsoft Teams com o Office 365. Se você tiver uma implantação local do Exchange Server ou do Skype for Business Server, configure a [autenticação moderna híbrida](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) com o Azure Active Directory (Azure AD) para habilitar o uso da autenticação moderna.

A autenticação moderna é compatível com as salas do Microsoft Teams versão 4.4.25.0 e posteriores.

## <a name="modern-authentication"></a>Autenticação moderna

Quando você usa a autenticação moderna com o aplicativo salas do Microsoft Teams, a Active Directory Authentication library (ADAL) é usada para conexão com o Microsoft Teams, o Exchange e o Skype for Business. Um dispositivo de salas do Microsoft Teams é um dispositivo compartilhado e executa uma reinicialização noturna para garantir o funcionamento sem problemas e obter um sistema operacional, Driver, firmware ou atualizações de aplicativo essenciais. O mecanismo de autenticação moderna usa o tipo de concessão de autorização de [credenciais de senha de proprietário do recurso](https://tools.ietf.org/html/rfc6749#section-1.3.3) no OAuth 2,0, que não requer intervenção do usuário. Essa é uma das principais diferenças entre a maneira como a autenticação moderna funciona para contas de usuário em relação às contas de recursos usadas pelo aplicativo salas do Microsoft Teams. Por isso, as contas de recursos de salas do Microsoft Teams não devem ser configuradas para usar a MFA (autenticação multifator), a autenticação de cartão inteligente ou a autenticação baseada em certificado de cliente (que estão disponíveis para usuários finais).

A outra diferença importante entre a maneira como a autenticação moderna funciona em dispositivos de salas do Microsoft Teams e dispositivos de usuário final é que você não pode usar uma conta de recurso para aplicar políticas de acesso condicional no nível do dispositivo, como "exigir que o dispositivo seja marcado como queixa" ou "exigir dispositivo híbrido Azure AD ingressou", e assim por diante. Isso ocorre porque os conceitos no nível do dispositivo não se aplicam à autenticação moderna quando usados no nível do aplicativo. Em vez disso, você pode registrar um dispositivo no Microsoft Intune e aplicar políticas de conformidade usando as diretrizes [aqui](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Habilitar a autenticação moderna em um dispositivo de salas do Microsoft Teams

Para salas do Microsoft Teams usar a autenticação moderna com o Skype for Business e o Exchange, habilite a configuração do lado do cliente para autenticação moderna no dispositivo de salas do Microsoft Teams. Você pode fazer isso nas configurações do dispositivo ou no arquivo XML de configuração.

> [!NOTE]
> Antes de habilitar a configuração do lado do cliente para autenticação moderna, certifique-se de que seu ambiente está configurado corretamente para usar a autenticação moderna.

### <a name="using-device-settings"></a>Usar as configurações do dispositivo

1. No dispositivo de salas da equipe da Microsoft, vá para **mais** (**..**.).
    
2. Selecione **configurações**e, em seguida, digite o nome de usuário e a senha do administrador do dispositivo.
3. Vá para a guia **conta** , ative a **autenticação moderna**e, em seguida, selecione **salvar e sair**.

### <a name="using-the-xml-config-file"></a>Usar o arquivo de configuração XML

No seu arquivo SkypeSettings. xml, defina o elemento XML de autenticação moderna como **verdadeiro**, da seguinte maneira.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar a configuração, consulte [gerenciar configurações de console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar seu ambiente para autenticação moderna

Antes de começar, certifique-se de que compreende os modelos de identidade a serem usados com o Office 365 e o Azure AD. Você pode encontrar mais informações nos [modelos de identidade do Office 365 e no Active Directory do Azure](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) e na [identidade híbrida e na sincronização de diretórios do Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-office-365"></a>Habilitar a autenticação moderna no Office 365

Para habilitar a autenticação moderna do Exchange Online, confira [habilitar a autenticação moderna no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Se você usa o Skype for Business Online, verifique também se a autenticação moderna está ativada para o Skype for Business online. Para saber mais, confira [Skype for Business Online: habilitar seu locatário para autenticação moderna](https://aka.ms/SkypeModernAuth).

Recomendamos que você não remova as políticas básicas de autenticação do Exchange Online ou desabilite a autenticação básica para o seu locatário antes de validar que os dispositivos de salas do Microsoft Teams podem entrar no Exchange Online e em Teams ou no Skype for Business online com êxito quando a configuração de autenticação moderna estiver ativa e se não houver dispositivos que ainda estejam configurados para usar a autenticação básica.

Para obter mais informações sobre como desabilitar a autenticação básica no Exchange Online, confira [desabilitar a autenticação básica no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticação moderna híbrida

Para garantir uma autenticação bem-sucedida para o Exchange Server local e/ou o Skype for Business Server, você deve verificar se a conta do recurso usada com as salas do Microsoft Teams está configurada para obter autorização do Azure AD. Para saber mais sobre a identidade híbrida e os métodos que funcionam para sua organização, leia os seguintes tópicos: 

- [O que é sincronização de hash de senha?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [O que é autenticação de passagem?](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [O que é Federação?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Pré-requisitos específicos para salas do Microsoft Teams

Os pré-requisitos para habilitar a autenticação moderna na sua topologia híbrida são abordados na [visão geral e pré-requisitos de autenticação moderna moderna para uso com o Skype for Business e Exchange Servers locais](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview). Todos os pré-requisitos discutidos no artigo se aplicam.

No entanto, como as salas do Microsoft Teams usam a autorização de [credenciais de senha de proprietário do recurso](https://tools.ietf.org/html/rfc6749#section-1.3.3) e as APIs REST subjacentes para autenticação moderna, as diferenças a seguir são importantes para salas de equipe da Microsoft.

- Você deve ter o Exchange Server 2016 CU8 ou posterior ou o Exchange Server 2019 CU1 ou posterior.
- Você deve ter o Skype for Business Server 2015 CU5 ou posterior, ou o Skype for Business Server 2019 ou posterior.
- A MFA não é suportada independentemente da topologia que você tem.
- Se você usar um provedor de autenticação de terceiros que seja compatível com o Azure AD, ele deve dar suporte ao OAuth e usar a autorização de credenciais de senha de proprietário do recurso.
- Não use políticas de acesso condicional no nível do dispositivo para uma conta de recurso configurada com o aplicativo. Isso resultará em falhas de entrada. Em vez disso, registre um dispositivo no Microsoft Intune e aplique políticas de conformidade usando as diretrizes publicadas [aqui](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).

### <a name="configure-exchange-server"></a>Configurar o Exchange Server

Para habilitar a autenticação moderna híbrida no Exchange Server, consulte [como configurar o Exchange Server local para usar a autenticação moderna híbrida](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurar o Skype for Business Server

Para habilitar a autenticação moderna híbrida com o Skype for Business Server, consulte [como configurar o Skype for Business no local para usar a autenticação moderna híbrida](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Remover ou desabilitar o Skype for Business e o Exchange

Se a sua configuração não permitir uma autenticação moderna híbrida ou você precisar remover ou desabilitar a autenticação moderna híbrida do Exchange ou do Skype for Business, consulte [remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Acesso condicional do Azure AD

Você pode configurar uma conta de recurso usada com as salas do Microsoft Teams para acesso baseado em IP/local. Para saber mais, veja [acesso condicional: bloquear o acesso por local](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Não há suporte para nenhuma outra política de acesso condicional. Para obter mais informações sobre a conformidade de dispositivos, consulte as diretrizes [aqui](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).  
