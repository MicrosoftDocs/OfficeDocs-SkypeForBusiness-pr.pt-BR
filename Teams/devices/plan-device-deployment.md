---
title: Planejar sua implantação para dispositivos de telefone e exibições do Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: Este artigo fornece uma visão geral das tarefas e etapas para implantar telefones e exibições do Teams em sua organização.
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 4ba5c1a9ab59765a5a0af2ac145baf69fc4a8a9a
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392511"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planejar sua implantação para dispositivos de telefone e exibições do Teams

Uma implantação bem-sucedida de dispositivos telefônicos do Teams e do Teams Displays começa com o planejamento. Este artigo levará você pelas tarefas e etapas para implantar esses dispositivos em sua organização. Ele também fornece diretrizes sobre uso, licenciamento, integração com seu ambiente, pontos de toque e gerenciamento.

> [!TIP]
> [O Microsoft Hub de Adoção 365](https://adoption.microsoft.com/) é um ótimo lugar para começar sua jornada de adoção com Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Tarefa 1: Quais são seus objetivos de implantação?

O planejamento da distribuição de telefones e exibições do Teams em sua organização começa com suas metas de implantação. Os dispositivos teams dão suporte ao trabalho híbrido em salas de reunião, escritórios e outros espaços funcionais. Você precisará determinar onde esses dispositivos serão usados e por quem.

### <a name="objective-identify-your-device-personas"></a>Objetivo: identificar as personas do dispositivo

Os telefones e displays do Teams se ajustarão a uma das duas personas: 

- Dispositivos pessoais
- Dispositivos de espaço compartilhado

Dispositivos pessoais e compartilhados têm funções e usos diferentes. 

**Dispositivos pessoais:** 

- Normalmente atribuído a um usuário, conectado com a conta desse usuário e habilitado com uma licença de recurso do Teams para acessar o serviço.
- Pense em dispositivos pessoais como tendo uma relação de um para um, com um dispositivo por usuário.
- Pode ser emparelhado com o cliente da área de trabalho do Teams e usar recursos como Better Together
- Pode se conectar a um headset, com fio ou sem fio
- Recursos adicionais em dispositivos pessoais incluem hot-desking e Home Screen. 

**Dispositivos de espaço compartilhado:**

- Execute uma função específica, como um telefone de área comum ou um dispositivo de sala de reunião e exija uma conta dedicada e uma licença de recurso para acessar o serviço.
- Pense em dispositivos compartilhados como tendo uma relação de um para muitos: um dispositivo compartilhado por muitos usuários.
- Implantado em espaços compartilhados, como salas de reunião, áreas de recepção ou pisos de fabricação. 
- Suas interfaces de usuário (interface do usuário) são específicas para sua função, como interface do usuário de telefone de área comum ou interface do usuário da sala de reunião dependem da função e posicionamento do dispositivo compartilhado.
- Exigir configuração e endurecimento opcional para garantir que as configurações não sejam alteradas ou para impedir que a conta saia. 
- Recursos adicionais em dispositivos de espaço compartilhado incluem pesquisa em telefones de área comum e hot-desking com tempo limite ocioso

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Objetivo: quantos dispositivos de espaço pessoal e compartilhado você precisa?

Agora que você identificou suas personas de dispositivo, você precisa determinar quais dispositivos certificados você deseja usar e quantos deles você precisa. Para ajudá-lo a tomar essa decisão, considere as seguintes perguntas: 

- Quantos dispositivos pessoais são necessários e quem terá um?
- Quantas salas ou espaços exigem dispositivos compartilhados? Cada espaço terá o mesmo tipo de dispositivo? 
- Seus dispositivos precisarão atender a requisitos específicos?
    - Exemplos incluem tamanho de tela, fator de formulário e fabricante ou modelo? Para obter uma lista de telefones e exibições certificados, consulte [Microsoft dispositivos certificados pelo Teams](teams-ip-phones.md).
-  Você precisa de telefones do Teams ou exibições do Teams? Para obter uma lista de recursos com suporte para telefones do Teams, consulte [Telefones para Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones). Para obter uma lista de recursos com suporte para exibições do Teams, consulte [Microsoft exibições do Teams](teams-displays.md#features-supported-by-teams-displays).
- Você tem dispositivos suficientes para novos usuários ou um processo para novos pedidos e entrega?
- Você terá dispositivos de reposição disponíveis para manutenção ou se um dispositivo tiver problemas de hardware? Ser capaz de trocar um dispositivo rapidamente evita interrupções na experiência do usuário.

## <a name="task-2-what-are-your-licensing-requirements"></a>Tarefa 2: Quais são seus requisitos de licenciamento? 

Agora você sabe quantos dispositivos você precisa, a próxima etapa é determinar quantas licenças são necessárias. Telefones e exibições do Teams exigem licenças para acessar Microsoft Teams e Microsoft 365.

Dispositivos compartilhados e pessoais precisam de licenciamento diferente. Para dispositivos pessoais, licenças atribuídas a contas de usuário podem ser usadas. Dispositivos compartilhados precisam de licenças específicas para sua função. Para telefones e exibições, as licenças aplicáveis são [a licença Microsoft Dispositivos Compartilhados do Teams](/microsoftteams/teams-add-on-licensing/teams-shared-device-license) e uma [licença de Salas do Microsoft Teams](../rooms/rooms-licensing.md).

Para obter mais informações e comparar suas opções de licenciamento, consulte [Microsoft 365 planos de licenciamento](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).

## <a name="task-3-what-are-your-dependencies"></a>Tarefa 3: Quais são suas dependências? 

### <a name="objective-plan-your-device-identities"></a>Objetivo: planejar as identidades do dispositivo

As identidades permitem que os dispositivos acessem Microsoft 365 serviços e devem facilitar a descoberta, gerenciamento e conexão de dispositivos em sua organização. Para fazer isso, considere o seguinte ao planejar identidades do dispositivo:

- Nomes de entidade de usuário e seu formato e domínio
- Nomes de exibição
- Descoberta de catálogo de endereços
- Tipos de dispositivo de espaço pessoal versus compartilhado
- Licenciamento atribuído por grupo versus usuário

### <a name="objective-review-conditional-access-policies"></a>Objetivo: examinar políticas de acesso condicional

As políticas de Acesso Condicional do Azure Active Directory são requisitos adicionais que devem ser atendidos antes que um dispositivo possa ser conectado.

Como você planeja sua implantação

- Examine as políticas de acesso condicional existentes que podem afetar seus telefones e exibições do Teams. Você pode fazer isso no Centro de Azure AD Administração usando a [ferramenta What If](/azure/active-directory/conditional-access/what-if-tool) e [os logs de](/azure/active-directory/reports-monitoring/concept-sign-ins) entrada

- Planejar novas regras, se necessário

- Use recursos de Acesso Condicional, como filtros de dispositivo, para aplicar regras a telefones e exibições do Teams.

>[!NOTE]
>Há algumas políticas de Acesso Condicional que os dispositivos Android não dão suporte. Para obter diretrizes e práticas recomendadas, consulte Dispositivos Android, consulte [Práticas recomendadas de autenticação para dispositivos Android do Teams](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>Tarefa 4: preparar seu ambiente

### <a name="objective-plan-network-basics"></a>Objetivo: Planejar noções básicas de rede

Dispositivos e exibições do Teams Phone exigem acesso à Internet para se conectar ao Teams e funcionar conforme o planejado. Para preparar sua rede para implantação, considere o seguinte:

- Sua infraestrutura de rede tem capacidade suficiente? Considere portas de comutador, pontos de acesso sem fio e outras coberturas.
- Se você usar VLANs e DHCP, seus escopos serão dimensionados de acordo?
- Avaliar e testar caminhos de rede de onde os dispositivos são implantados para Microsoft 365. 
- Abra as portas e URLs de firewall necessárias para Microsoft 365 de acordo com as diretrizes.
- Examine e teste os requisitos e a configuração do E911 para precisão e conformidade do local. 
- Evite usar um servidor proxy e otimizar caminhos de mídia para confiabilidade e qualidade.

### <a name="objective-physical-considerations"></a>Objetivo: considerações físicas

Considere os espaços físicos nos quais seus telefones e exibições do Teams serão usados.

Os principais aspectos incluem

- **Poder:** Você tem tomadas elétricas suficientes? Se o dispositivo precisar de uma fonte de energia externa, quão perto você pode posicioná-lo em uma tomada?
- **Posicionamento do dispositivo:** Onde seu dispositivo estará fisicamente? Revise estandes de mesa, montagens de parede e outros acessórios do fabricante de equipamentos original (OEM).
- **Segurança:** Seu dispositivo precisa ser bloqueado em determinados espaços?
- **Acessibilidade:** O dispositivo atende aos requisitos de acessibilidade de seu usuário primário? Considere onde ele é colocado, o comprimento do fio e a usabilidade do fone de ouvido ou do fone de ouvido.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Tarefa 5: como você gerenciará dispositivos implantados?

Os telefones e displays do Teams são gerenciados de dois a três portais Microsoft 365 e seus respectivos módulos do PowerShell: 

#### <a name="azure-active-directory-admin-center"></a>Centro de Administração do Azure Active Directory

Usar o Centro de Azure AD Administração para gerenciar

- Todas as tarefas relacionadas à identidade para telefones e exibições do Teams
- Políticas de acesso condicional 
- Redefinições de senha

#### <a name="teams-admin-center"></a>Centro de Administração do Teams

Usar o Centro de Administração do Teams para gerenciar

- [Configurações do dispositivo para o Teams](../business-voice/manage-devices.md)
- [Perfis de configuração](device-management.md#use-configuration-profiles-in-teams)
- [Marcação de dispositivo](manage-device-tags.md)
- [Entrada remota e saída](remote-sign-in-and-sign-out.md)
- Análise de chamadas  
- Firmware
- Solução de problemas e download de logs

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Central de Administração do Endpoint Manager (se você usar Intune para gerenciamento de dispositivos)

Use o Centro de Administração do Endpoint Manager para gerenciar: 

- Políticas de conformidade do dispositivo
- Restrições de registro
- Identificadores de dispositivo corporativo
- Filtros de dispositivo
