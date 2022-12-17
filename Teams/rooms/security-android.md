---
title: Microsoft segurança do Teams para Android
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Saiba como proteger seu Microsoft Teams para dispositivos Android.
ms.openlocfilehash: 044ff85a39058df85a1f132aaac08bb1d87c6c95
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438566"
---
# <a name="microsoft-teams-for-android-security"></a>Microsoft segurança do Teams para Android

Este artigo não abrange dispositivos Android configurados para modo de dispositivo dedicado por Microsoft Endpoint Manager. Os dispositivos Android do Teams são executados no modo quiosque por design. Para obter informações sobre o Android Kiosk, confira [Registro de dispositivo dedicado do Android Enterprise](/mem/intune/enrollment/android-kiosk-enroll).

Microsoft trabalha com nossos parceiros OEM para fornecer uma solução segura por design e personalizável para atender às necessidades do cliente. Este artigo discute muitos dos recursos de segurança encontrados em dispositivos Android do Teams e nossa abordagem. Ele é dividido em quatro seções-chave para facilitar a navegação.

> [!NOTE]
> Microsoft dispositivos Android do Teams não devem ser tratados como um dispositivo Android típico. Os dispositivos Android do Teams são dispositivos criados com propósito projetados para uso com o Teams e seus respectivos casos de uso. Este artigo se aplica a dispositivos do Teams Microsoft certificados e dedicados que executam apenas o sistema operacional Android. Os dispositivos certificados pelo Teams só podem ser comprados de fornecedores OEM certificados. Para obter informações sobre Microsoft dispositivos Android certificados pelo Teams, consulte [Microsoft dispositivos Android certificados pelo Teams](/microsoftteams/devices/teams-ip-phones).

Para obter informações sobre segurança em Salas do Teams em dispositivos Windows, consulte [Salas do Microsoft Teams na segurança do Windows](security-windows.md).

## <a name="software-security"></a>Segurança de software

### <a name="android-kiosk-mode"></a>Modo de quiosque Android

Os dispositivos Android do Teams são bloqueados para executar apenas aplicativos aprovados executando o dispositivo no modo Quiosque android. O modo de quiosque desabilita o acesso a todos os recursos do inicializador e ajuda a proteger o dispositivo para que aplicativos autorizados sejam iniciados no dispositivo.  

| Nome do Aplicativo            | Descrição do aplicativo                   |
|-----------------------------|-------------------------------------------|
| Microsoft Aplicativo Android do Teams | Microsoft Aplicativo de Dispositivo do Teams        |
| Agente de Administração do Microsoft teams | Gerenciamento Remoto do Centro de Administração do Teams      |
| Portal da Empresa do Intune       | Registro de Dispositivo, Registro & Entrada |
| Agente de Parceiro OEM           | Aplicativo de configurações de dispositivo & agente do parceiro OEM   |

Por design, o aplicativo Android do Microsoft Teams será iniciado na inicialização no modo quiosque do Android e não fornece ao usuário qualquer acesso ao sistema operacional ou acesso a componentes fora da experiência de usuário designada do Teams.

### <a name="application-code-signing"></a>Assinatura de código do aplicativo

Todos os aplicativos Microsoft e OEM são assinados por código. A assinatura de código auxilia na validação de que o software em execução em um dispositivo é genuíno de Microsoft e de nossos parceiros de hardware. A assinatura de código também tenta validar a integridade do software que está sendo executado no dispositivo, de modo que apenas o software genuíno possa ser iniciado e executado.  

### <a name="third-party-applications"></a>Aplicativos de terceiros

Os dispositivos certificados pelo Teams não têm o Google Play Store, o Amazon App Store ou o Google Play Services, instalados por design. Isso ajuda a garantir que nenhum aplicativo de terceiros possa ser instalado do repositório em um dispositivo.  

### <a name="android-debug-bridge"></a>Ponte de depuração do Android

A ponte de depuração do Android (ADB) é desabilitada pelo design em todos os dispositivos Android do Teams que executam o software de versão. O ADB é uma ferramenta de linha de comando que permite que os administradores executem funções em dispositivos baseados em Android e habilita a instalação de aplicativos, acesso ao shell do dispositivo e outras funções de administrador.  

### <a name="file-system-encryption"></a>Criptografia do sistema de arquivos

Os dispositivos Android do Teams devem dar suporte à criptografia baseada em Android e podem ser aplicados usando Microsoft políticas de conformidade do Endpoint Manager. Para obter informações sobre políticas de conformidade do Endpoint Manager[, use políticas de conformidade do Endpoint Manager para definir regras para dispositivos que você gerencia com Intune](/mem/intune/protect/device-compliance-get-started).

### <a name="android-os-version"></a>Versão do sistema operacional Android

Os dispositivos Android do Teams executam versões com suporte do Android. O sistema operacional Android é gerenciado por parceiros OEM, mesclado em firmware certificado pelo Teams e, em seguida, enviado por push para dispositivos do centro de administração do Teams. Para obter informações sobre quais versões do Android estão sendo executadas em dispositivos Android do Teams, consulte [Microsoft dispositivos Android certificados pelo Teams](/microsoftteams/devices/teams-ip-phones).

### <a name="android-security-updates"></a>Atualizações de segurança do Android

Os fornecedores OEM, como parte do processo de atualização de firmware, incorporam as linhas de base de atualização de segurança do Android apropriadas para ajudar a garantir que o sistema operacional base seja mantido seguro. Manter seus dispositivos atualizados regularmente é importante para garantir que as atualizações de segurança apropriadas do Android estejam em execução em seus dispositivos. Para obter mais informações, consulte o fabricante do dispositivo.

### <a name="account-security"></a>Segurança da conta

Os dispositivos Android do Teams são criados em torno de dois tipos de contas que permitem o funcionamento bem-sucedido de um dispositivo.

- Conta de administrador de dispositivo local

- Conta de usuário ou recurso  

Os dispositivos Android do Teams também são compatíveis com algumas políticas de acesso condicional, que podem ser usadas como camadas adicionais de segurança para entrada do dispositivo. Para melhores práticas e políticas de acesso condicional com suporte, consulte [Políticas de conformidade de acesso condicional com suporte](/microsoftteams/rooms/supported-ca-and-compliance-policies).

### <a name="local-device-administrator-account"></a>Conta de administrador de dispositivo local

Os dispositivos Android do Teams incluem uma conta administrativa para acessar as configurações do dispositivo, o servidor Web local se estiver instalado e quaisquer configurações específicas do OEM.

Itens iniciais de configuração e configuração do dispositivo, como o nome de usuário padrão e a senha dessa conta, podem ser obtidos do fabricante do dispositivo.

> [!CAUTION]
> Certifique-se de alterar a senha do administrador de dispositivo local o mais rápido possível.  

> [!TIP]
> O centro de administração do Teams pode ser usado para alterar a senha de administrador de dispositivo local de um dispositivo Android do Teams conectado aplicando um perfil de configuração. Recomendamos essa abordagem após a entrada inicial do dispositivo para proteger recursos elevados de um dispositivo Android. Recursos elevados podem incluir configurações de dispositivo e portais de administração da Web se tiverem suporte.

### <a name="user-or-resource-account"></a>Conta de usuário ou recurso

Os dispositivos Android do Teams exigem o uso de uma conta de recurso dedicada ou de usuário para entrar no Microsoft 365. Tentamos proteger essas contas de maneiras específicas, dependendo se for uma conta de usuário normal para um dispositivo pessoal ou uma conta de recurso para um dispositivo compartilhado. Para obter mais informações, consulte [Criar e configurar contas de recursos para salas e dispositivos compartilhados](/microsoftteams/rooms/with-office-365).

### <a name="device-updates"></a>Atualizações de dispositivo

Os dispositivos Android do Teams são configurados para baixar atualizações certificadas por Microsoft do centro de administração do Teams quando estiverem disponíveis. Elas podem ser enviadas por push automaticamente ou manualmente invocadas por um Administrador. Ferramentas de terceiros de nossos parceiros OEM também estão disponíveis para executar essa função, se necessário. Os dispositivos Android do Teams podem instalar atualizações após o expediente para evitar impacto para os usuários. Os agendamentos após o expediente podem ser configurados no centro de administração do Teams ou usando ferramentas de terceiros de parceiros OEM.

> [!IMPORTANT]
> Microsoft recomenda que o gerenciamento de firmware para todos os dispositivos Android do Teams seja feito por meio do centro de administração do Teams.

## <a name="network-security"></a>Segurança de rede

Os dispositivos Android do Teams têm os mesmos requisitos de rede que qualquer cliente do Microsoft Teams, incluindo acesso por meio de firewalls e outros dispositivos de segurança. Especificamente, as categorias listadas conforme **necessário** para o Teams devem estar abertas no firewall, juntamente com outros serviços de suporte, conforme listado abaixo. Para obter a lista completa de IPs e URLs necessárias para dispositivos Android do Teams, confira:

- Microsoft Teams, Exchange Online, SharePoint Online, Microsoft 365 Common e [Office Online Office 365 URLs e intervalo de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Microsoft Intune [pontos de extremidade de rede para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Os dispositivos Android do Teams funcionam com a maioria dos protocolos de segurança baseados em rede 802.1X e outros. No entanto, não podemos testar dispositivos Android do Teams em todas as configurações de segurança de rede. Portanto, se surgirem problemas de desempenho que podem ser rastreados para problemas de desempenho de rede, talvez seja necessário desabilitar esses protocolos se eles estiverem configurados em sua organização ou entrar em contato com seu parceiro OEM para obter assistência.

Para o melhor desempenho da mídia em tempo real, recomendamos que você configure o tráfego de mídia do Teams para ignorar servidores proxy e outros dispositivos de segurança de rede. A mídia em tempo real é sensível à latência de rede, que pode ser causada por servidores proxy e outros dispositivos de segurança de rede. A latência de rede pode degradar significativamente a qualidade de áudio e vídeo dos usuários. Para obter mais informações, consulte [Networking up (para a nuvem) — Um ponto de vista do arquiteto](/microsoft-365/solutions/networking-design-principles) que discute recomendações de rede para melhorar o desempenho da mídia com Microsoft Teams.

Os dispositivos Android do Teams usam comunicações criptografadas e autenticação de ponto de extremidade na Internet. Os dispositivos Android do Teams usam o TLS 1.2+.  

> [!IMPORTANT]
> Os dispositivos Android do Teams não dão suporte a servidores proxy autenticados ou restrições de locatário. Entre em contato com seu parceiro OEM para obter informações de suporte a proxy.

Os dispositivos Android do Teams não precisam se conectar a uma LAN interna. Considere colocar dispositivos Android do Teams em um segmento de rede seguro com acesso direto à Internet. Por exemplo, os Telefones do Teams podem ser implantados em uma VLAN de voz. Se sua LAN interna ficar comprometida, as oportunidades de vetor de ataque para dispositivos Android do Teams serão reduzidas implementando essa segregação de rede.

Recomendamos fortemente que você conecte seus dispositivos Android do Teams a uma rede com fio. O uso de redes sem fio requer um planejamento e avaliação cuidadosos para a melhor experiência.

Junção de proximidade, Melhores Juntos, Elenco do Teams e emparelhamento de painéis do Teams dependem do Bluetooth. O uso de tecnologia Bluetooth em Salas do Teams em dispositivos Android está atualmente limitado a sinalizadores de publicidade e conexões proximal solicitadas. O `ADV_NONCONN_INT` tipo PDU (unidade de dados de protocolo) é usado no sinalizador de publicidade. Esse tipo de PDU é para dispositivos não conectáveis que anunciam informações para o dispositivo ouvinte. Não há emparelhamento de dispositivo Bluetooth como parte desses recursos. Detalhes adicionais sobre protocolos Bluetooth podem ser encontrados no site do SIG Bluetooth.

O Teams Phones and Displays oferece capacidade de emparelhamento Bluetooth para emparelhar com fones de ouvido usando o Perfil de Hands-Free Bluetooth.

Para obter mais informações sobre segurança no Microsoft Teams, consulte [Equipes de Segurança e Microsoft](/microsoftteams/teams-security-guide).  
