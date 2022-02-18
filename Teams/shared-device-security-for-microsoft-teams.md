---
title: 'Guia de segurança do Microsoft Teams: use o Teams com segurança em computadores compartilhados'
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Orientações para usar o Microsoft Teams de forma segura em um computador compartilhado no local de trabalho.
ms.localizationpriority: high
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
ms.openlocfilehash: c97ebd8cf9e43ada8d077ffbd33f6b39c8d9c64c
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893540"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Usar o Microsoft Teams de forma segura em computadores compartilhados

Sempre que possível, é *recomendável* que as empresas usem uma abordagem de Confiança Zero para dispositivos dos clientes que usam recursos de gerenciamento de dispositivos, verificações de integridade do dispositivo e imposição de política, criptografia no nível do dispositivo e outros recursos de segurança.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Imagem de Confiança Zero mostrando explicitamente a verificação, privilégios mínimos, e a suposição de violação (os principais princípios da Confiança Zero) nos círculos azuis.":::

Os administradores podem criar condições muito seguras, *insistindo* na verificação, no privilégio mínimo e presumindo padrões de comprometimento que levem a ações que minimizem o risco para os usuários e dados.

> [!TIP]
> Para uma análise mais profunda dos princípios de Confiança Zero, confira [esses vídeos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Dicas para usar o Microsoft Teams de forma segura em um computador compartilhado

Reconhecendo que isso possa não ser possível ou prático em todos os cenários, ainda é importante que os administradores de segurança entendam a orientação para usar o Teams de um computador compartilhado ou de um dispositivo não gerenciado da melhor forma possível.

Os planos devem ser desenvolvidos para seguir as orientações da maneira mais rápida possível.

1. Usar os recursos de segurança da plataforma do sistema operacional.
    1. Verifique se o sistema operacional está configurado para instalar as atualizações automáticas do provedor do sistema operacional (para os sistemas da Microsoft, isso pode ser feito por meio do [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    1. Verifique se quaisquer recursos de criptografia de dispositivo, como o [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) estão habilitados e a chave usada para acessar o dispositivo é protegida.  Observe que a maioria dos [**dispositivos Windows 10 dá suporte ao bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10). 
    1. Use recursos antivírus, como os oferecidos pelo [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) em seus dispositivos.
    1. É altamente recomendável usar o [contas de usuário separadas](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) para cada usuário do sistema.
    1. *Não* conceda nem use privilégios de administrador para funções não administrativas (como navegar na Web, executar o Teams, etc).

Se as diretrizes acima não puderem ser atendidas, recomendamos que você use as práticas recomendadas de segurança adicionais do navegador:

1. Aplicar os recursos de segurança do navegador.
    1. Use sessões de navegação privadas para minimizar os dados e o histórico que continuam no disco. Por exemplo, use a [navegação InPrivate no Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [a navegação incógnita no Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)ou os recursos do seu navegador específico para navegar em privado. 
    1. É recomendável alterar o comportamento do sistema para acionar a navegação privada *por padrão*. 

2. Navegue até e use o [aplicativo Web do Teams](https://teams.microsoft.com) (às vezes conhecido como cliente *web*) não o cliente para download do Teams.

3. Quando terminar de usar o sistema compartilhado, você deve: 
    1. [Sair do Microsoft Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Fechar todas as guias e janelas do navegador.
    1. Sair do dispositivo.

Os itens acima não são uma lista completa das práticas recomendadas ou dos controles de segurança que abrangem todos os casos, e podem haver ações adicionais que podem ser tomadas em seu ambiente (por exemplo, os administradores de segurança podem optar por usar Links Seguros e Anexos Seguros para o Teams, caso você tenha [o plano 1 ou 2 de Proteção Avançada contra Ameaças do Office 365](/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)). Mas essas etapas são só um ponto de partida para construir orientações para usar o Teams em dispositivos compartilhados.

## <a name="more-information"></a>Mais informações

[BitLocker no Gerenciador de Configurações](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker para Windows 10 no Intune](/mem/intune/protect/encrypt-devices)

[Segurança do ponto de extremidade no Intune](/mem/intune/protect/endpoint-security)

[Habilitar o](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus na Segurança do Windows e [executar exames](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app).

[Artigo do Centro de Segurança do Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Cliente Web do Teams/aplicativo Web do Teams](./get-clients.md#browser-client)

[Segurança e o Microsoft Teams](./teams-security-guide.md)
