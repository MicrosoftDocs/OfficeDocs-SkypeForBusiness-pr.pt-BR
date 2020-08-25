---
title: Guia de Segurança do Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Orientações para usar o Microsoft Teams de forma segura em um computador compartilhado no local de trabalho.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3486df0ca12303a9351c756df4184f160e95ab34
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868690"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Usar o Microsoft Teams de forma segura em computadores compartilhados

Sempre que possível, é *recomendável* que as empresas usem uma abordagem de Confiança Zero para dispositivos dos clientes que usam recursos de gerenciamento de dispositivos, verificações de integridade do dispositivo e imposição de política, criptografia no nível do dispositivo e outros recursos de segurança.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Imagem de Confiança Zero mostrando explicitamente a verificação, privilégios mínimos, e a suposição de violação (os principais princípios da Confiança Zero) nos círculos azuis.":::

Os administradores podem criar condições muito seguras, *insistindo* na verificação, no privilégio mínimo e supondo padrões de comprometimento que levem a ações que minimizem o risco para os usuários e dados.

> [!TIP]
> Para uma análise mais profunda dos princípios de Confiança Zero, confira [esses vídeos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Dicas para usar o Microsoft Teams de forma segura em um computador compartilhado

Reconhecendo que isso possa não ser possível ou prático em todos os cenários, ainda é importante que os administradores de segurança entendam a orientação para usar o Teams de um computador compartilhado ou de um dispositivo não gerenciado da melhor forma possível.

Os planos devem ser desenvolvidos para seguir as orientações da maneira mais rápida possível.

1. Usar os recursos de segurança da plataforma do sistema operacional.
    1. Verifique se o sistema operacional está configurado para instalar as atualizações automáticas do provedor do sistema operacional (para os sistemas da Microsoft, isso pode ser feito por meio do [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    2. Certifique-se de que todos os recursos de criptografia, como [**BitLocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) estão habilitados, e a chave usada para acessar o dispositivo está protegida.  Observe que a maioria dos mais modernos [**dispositivos Windows 10 oferecem suporte ao BitLocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10). 
    1. Use recursos antivírus, como os oferecidos pelo [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) em seus dispositivos.
    1. É altamente recomendável usar o [contas de usuário separadas](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) para cada usuário do sistema.
    1. *Não* conceda nem use privilégios de administrador para funções não administrativas (como navegar na Web, executar o Teams, etc).

2. Aproveitar os recursos de segurança do navegador.
    1. Use sessões de navegação privadas para minimizar os dados e o histórico que continuam no disco. Por exemplo, use a [navegação InPrivate no Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [a navegação incógnita no Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)ou os recursos do seu navegador específico para navegar em privado. 
    1. É recomendável alterar o comportamento do sistema para acionar a navegação privada *por padrão*. 

3. Navegue até e use o[aplicativo Web do Teams](https://teams.microsoft.com) (às vezes conhecido como cliente *web*) não o cliente para download do Teams.

4. Quando terminar de usar o sistema compartilhado, você deve: 
    1. [Sair do Microsoft Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Fechar todas as guias e janelas do navegador.
    1. Sair do dispositivo.

Os itens acima não são uma lista completa das práticas recomendadas ou dos controles de segurança que abrangem todos os casos, e podem haver ações adicionais que podem ser tomadas em seu ambiente (por exemplo, os administradores de segurança podem optar por usar links seguros e anexos seguros para o Teams, caso você tenha [o plano 1 ou 2 de Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)). No entanto, essas etapas são um ponto de partida para a criação de orientações para usar o Teams de dispositivos compartilhados.

## <a name="more-information"></a>Mais informações

[BitLocker no Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker para Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[Segurança do ponto de extremidade no Intune](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

[Habilitar o](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus na Segurança do Windows e [executar exames](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app).

[Artigo do Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Cliente Web do Teams/aplicativo Web do Teams](https://docs.microsoft.com/microsoftteams/get-clients#web-client)

[Segurança e o Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide)
