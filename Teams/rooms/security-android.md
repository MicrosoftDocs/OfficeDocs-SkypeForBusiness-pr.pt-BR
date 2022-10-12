---
title: Segurança do Microsoft Teams para Android
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
description: Saiba como proteger o Microsoft Teams para dispositivos Android.
ms.openlocfilehash: 6d17cc68af8ef4a879d5de3b17d27f20b281ddf8
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532431"
---
# <a name="microsoft-teams-for-android-security"></a>Segurança do Microsoft Teams para Android

Este artigo não aborda os dispositivos Android configurados para o modo de dispositivo dedicado pelo Microsoft Endpoint Manager. Os dispositivos Android do Teams são executados no modo quiosque por design. Para obter informações sobre o Quiosque do Android, confira [o registro de dispositivo dedicado do Android Enterprise](/mem/intune/enrollment/android-kiosk-enroll).

A Microsoft trabalha com nossos parceiros OEM para fornecer uma solução segura por design e personalizável para atender às necessidades do cliente. Este artigo aborda muitos dos recursos de segurança encontrados em dispositivos Android do Teams e nossa abordagem. Ele é dividido em quatro seções principais para facilitar a navegação.

> [!NOTE]
> Os dispositivos Android do Microsoft Teams não devem ser tratados como um dispositivo Android típico. Os dispositivos Android do Teams são dispositivos criados para uso com o Teams e seus respectivos casos de uso. Este artigo se aplica a dispositivos Microsoft Teams certificados e dedicados que executam apenas o sistema operacional Android. Os dispositivos certificados pelo Teams só podem ser comprados de fornecedores de OEM certificados. Para obter informações sobre dispositivos Android certificados pelo Microsoft Teams, consulte [dispositivos Android certificados pelo Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

Para obter informações sobre segurança no Salas do Teams para dispositivos Windows, [consulte Salas do Microsoft Teams para segurança do Windows](security-windows.md).

## <a name="software-security"></a>Segurança de software

### <a name="android-kiosk-mode"></a>Modo de quiosque do Android

Os dispositivos Android do Teams são bloqueados para executar somente aplicativos aprovados executando o dispositivo no modo de quiosque do Android. O modo de quiosque desabilita o acesso a todos os recursos do inicializador e ajuda a proteger o dispositivo para que os aplicativos autorizados iniciem no dispositivo.  

| Nome do Aplicativo            | Descrição do aplicativo                   |
|-----------------------------|-------------------------------------------|
| Aplicativo Android do Microsoft Teams | Aplicativo de Dispositivo do Microsoft Teams        |
| Microsoft Teams Administração Agent | Gerenciamento Remoto do centro de administração do Teams      |
| Portal da Empresa do Intune       | Registro de dispositivo, registro & entrada |
| Agente de Parceiro do OEM           | OEM Partner Agent & de Configurações do Dispositivo   |

Por design, o aplicativo Android do Microsoft Teams será iniciado na inicialização no modo de quiosque do Android e não fornecerá ao usuário acesso ao sistema operacional ou acesso a componentes fora da experiência do usuário designada do Teams.

### <a name="application-code-signing"></a>Assinatura de código do aplicativo

Todos os aplicativos Microsoft e OEM são assinados por código. A assinatura de código ajuda a validar que o software em execução em um dispositivo é original da Microsoft e de nossos parceiros de hardware. A assinatura de código também tenta validar a integridade do software que está sendo executado no dispositivo, de modo que somente o software original possa ser iniciado e executado.  

### <a name="third-party-applications"></a>Aplicativos de terceiros

Os dispositivos certificados do Teams não têm a Google Play Store, o Amazon App Store ou o Google Play Services, instalados por design. Isso ajuda a garantir que nenhum aplicativo de terceiros possa ser instalado da loja em um dispositivo.  

### <a name="android-debug-bridge"></a>Ponte de depuração do Android

A ADB (ponte de depuração do Android) está desabilitada por design em todos os dispositivos Android do Teams que executam o software de lançamento. O ADB é uma ferramenta de linha de comando que permite que os administradores executem funções em dispositivos baseados em Android e permite a instalação de aplicativos, o acesso ao shell do dispositivo e outras funções de administrador.  

### <a name="file-system-encryption"></a>Criptografia do sistema de arquivos

Os dispositivos Android do Teams devem dar suporte à criptografia baseada em Android e podem ser aplicados usando políticas de conformidade Endpoint Manager Microsoft. Para obter informações sobre Endpoint Manager de conformidade[, use Endpoint Manager de conformidade](/mem/intune/protect/device-compliance-get-started) para definir regras para dispositivos gerenciados com Intune.

### <a name="android-os-version"></a>Versão do sistema operacional Android

Os dispositivos Android do Teams executam versões compatíveis do Android. O sistema operacional Android é gerenciado por parceiros OEM, mesclado ao firmware certificado do Teams e enviado por push para dispositivos do centro de administração do Teams. Para obter informações sobre quais versões do Android estão em execução em dispositivos Android do Teams, consulte [dispositivos Android certificados pelo Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

### <a name="android-security-updates"></a>Atualizações de segurança do Android

Os fornecedores OEM, como parte do processo de atualização de firmware, incorporam as linhas de base de atualização de segurança do Android apropriadas para ajudar a garantir que o sistema operacional base seja mantido seguro. Manter seus dispositivos atualizados regularmente é importante para garantir que as atualizações de segurança do Android apropriadas estejam em execução em seus dispositivos. Para obter mais informações, consulte o fabricante do dispositivo.

### <a name="account-security"></a>Segurança da conta

Os dispositivos Android do Teams são criados em torno de dois tipos de contas que permitem o funcionamento bem-sucedido de um dispositivo.

- Conta de administrador do dispositivo local

- Conta de usuário ou recurso  

Os dispositivos Android do Teams também são compatíveis com algumas políticas de acesso condicional, que podem ser usadas como camadas adicionais de segurança para entrada do dispositivo. Para obter melhores práticas e políticas de acesso condicional com suporte, consulte [Políticas de conformidade de acesso condicional com suporte](/microsoftteams/rooms/supported-ca-and-compliance-policies).

### <a name="local-device-administrator-account"></a>Conta de administrador do dispositivo local

Os dispositivos Android do Teams incluem uma conta administrativa para acessar as configurações do dispositivo, o servidor Web local, se um estiver instalado, e quaisquer configurações específicas do OEM.

Os itens iniciais de configuração e configuração do dispositivo, como o nome de usuário e a senha padrão dessa conta, podem ser obtidos do fabricante do dispositivo.

> [!CAUTION]
> Certifique-se de alterar a senha do administrador do dispositivo local assim que possível.  

> [!TIP]
> O centro de administração do Teams pode ser usado para alterar a senha de administrador de dispositivo local de um dispositivo Android do Teams conectado aplicando um perfil de configuração. Recomendamos essa abordagem após a entrada inicial do dispositivo para proteger recursos elevados de um dispositivo Android. Os recursos elevados podem incluir configurações de dispositivo e portais de administração da Web, se houver suporte.

### <a name="user-or-resource-account"></a>Conta de usuário ou recurso

Os dispositivos Android do Teams exigem o uso de um usuário ou uma conta de recurso dedicada para entrar no Microsoft 365. Tentaremos proteger essas contas de maneiras específicas, dependendo se for uma conta de usuário normal para um dispositivo pessoal ou uma conta de recurso para um dispositivo compartilhado. Para obter mais informações, consulte [Criar e configurar contas de recursos para salas e dispositivos compartilhados](/microsoftteams/rooms/with-office-365).

### <a name="device-updates"></a>Atualizações de dispositivo

Os dispositivos Android do Teams são configurados para baixar atualizações certificadas pela Microsoft do centro de administração do Teams quando estiverem disponíveis. Eles podem ser enviados por push automaticamente ou manualmente invocados por um Administrador. Ferramentas de terceiros de nossos parceiros OEM também estão disponíveis para executar essa função, se necessário. Os dispositivos Android do Teams podem instalar atualizações após o horário comercial para evitar o impacto nos usuários. Os agendamentos de horas extras podem ser configurados no centro de administração do Teams ou usando ferramentas de terceiros de parceiros OEM.

> [!IMPORTANT]
> A Microsoft recomenda que o gerenciamento de firmware para todos os dispositivos Android do Teams seja feito por meio do centro de administração do Teams.

## <a name="network-security"></a>Segurança de rede

Os dispositivos Android do Teams têm os mesmos requisitos de rede que qualquer cliente do Microsoft Teams, incluindo o acesso por meio de firewalls e outros dispositivos de segurança. Especificamente, as categorias listadas **conforme necessário** para o Teams devem estar abertas no firewall, juntamente com outros serviços de suporte, conforme listado abaixo. Para obter a lista completa de IPs e URLs necessários para dispositivos Android do Teams, consulte:

- Microsoft Teams, Exchange Online, SharePoint Online, Microsoft 365 Common e Office Online Office 365 [URLs e intervalo de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Microsoft Intune [pontos de extremidade de rede para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Os dispositivos Android do Teams funcionam com a maioria do 802.1X e outros protocolos de segurança baseados em rede. No entanto, não podemos testar dispositivos Android do Teams em todas as configurações de segurança de rede. Portanto, se surgirem problemas de desempenho que possam ser rastreados para problemas de desempenho de rede, talvez seja necessário desabilitar esses protocolos se eles estiverem configurados em sua organização ou entrar em contato com seu parceiro OEM para obter assistência.

Para obter um desempenho ideal de mídia em tempo real, é altamente recomendável configurar o tráfego de mídia do Teams para ignorar servidores proxy e outros dispositivos de segurança de rede. A mídia em tempo real é sensível à latência de rede, que pode ser causada por servidores proxy e outros dispositivos de segurança de rede. A latência de rede pode prejudicar significativamente a qualidade de áudio e vídeo dos usuários. Para obter mais informações, consulte Rede até (para a nuvem [) —](/microsoft-365/solutions/networking-design-principles) Ponto de vista de um arquiteto que discute as recomendações de rede para melhorar o desempenho da mídia com o Microsoft Teams.

Os dispositivos Android do Teams usam comunicações criptografadas e autenticação de ponto de extremidade na Internet. Os dispositivos Android do Teams usam o TLS 1.2+.  

> [!IMPORTANT]
> Os dispositivos Android do Teams não dão suporte a servidores proxy autenticados ou restrições de locatário. Entre em contato com seu parceiro OEM para obter informações de suporte de proxy.

Os dispositivos Android do Teams não precisam se conectar a uma LAN interna. Considere colocar dispositivos Android do Teams em um segmento de rede seguro com acesso direto à Internet. Por exemplo, os Telefones do Teams podem ser implantados em uma VLAN de voz. Se sua LAN interna for comprometida, as oportunidades de vetor de ataque para dispositivos Android do Teams serão reduzidas com a implementação dessa segregação de rede.

É altamente recomendável que você conecte seus dispositivos Android do Teams a uma rede com fio. O uso de redes sem fio requer planejamento e avaliação cuidadosos para a melhor experiência.

O Ingresso por Proximidade, o Better Together, o Teams Cast e o emparelhamento de painéis do Teams dependem do Bluetooth. Atualmente, o uso da tecnologia Bluetooth Salas do Teams para dispositivos Android está limitado a sinalizadores de publicidade e conexões sem fio solicitadas. O `ADV_NONCONN_INT` tipo de PDU (unidade de dados de protocolo) é usado no sinalizador de publicidade. Esse tipo de PDU é para dispositivos não conectáveis que anunciam informações para o dispositivo de escuta. Não há emparelhamento de dispositivo Bluetooth como parte desses recursos. Detalhes adicionais sobre protocolos Bluetooth podem ser encontrados no site do Bluetooth SIG.

Os Telefones e Telas do Teams oferecem capacidade de emparelhamento Bluetooth para emparelhar com fones de ouvido usando o Perfil de Hands-Free Bluetooth.

Para obter mais informações sobre segurança no Microsoft Teams, consulte [Segurança e Microsoft Teams](/microsoftteams/teams-security-guide).  
