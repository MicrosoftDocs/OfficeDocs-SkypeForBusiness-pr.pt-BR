---
title: Segurança de salas do Microsoft Teams
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Saiba como proteger seus dispositivos de salas do Microsoft Teams.
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880863"
---
# <a name="microsoft-teams-rooms-security"></a>Segurança de salas do Microsoft Teams

A Microsoft trabalha com nossos parceiros para oferecer uma solução segura e não requer ações adicionais para proteger as salas do Microsoft Teams. Este artigo discute muitos dos recursos de segurança encontrados nas salas de equipe.

> [!NOTE]
> As salas do Microsoft Teams não devem ser tratadas como uma estação de trabalho de usuário final típica. Não só os casos de uso são muito diferentes, mas os perfis de segurança padrão também são muito diferentes.

Os dados do usuário final limitados são armazenados em salas de equipe. Os dados do usuário final podem ser armazenados nos arquivos de log para solução de problemas e suporte apenas. Em nenhum momento, um participante de uma reunião pode copiar arquivos para a unidade de disco rígido ou conectar-se por meio de suas próprias salas de equipe. Não é possível transferir dados do usuário final para o dispositivo de salas do Microsoft Teams.

Embora os usuários finais não possam colocar arquivos em um disco rígido de salas de equipe, o Microsoft defender ainda está habilitado. O desempenho das salas de equipe é testado com o Microsoft defender. A desativação ou adição do software de segurança do ponto de extremidade pode levar a resultados imprevisíveis e degradação de sistema potencial.

## <a name="hardware-security"></a>Segurança de hardware

Em um ambiente de salas do Teams, há um módulo de computação central que executa o Windows 10 IoT Enterprise Edition. Cada módulo de computação certificado deve ter uma solução de montagem segura, um slot de trava de segurança (por exemplo, Kensington Lock) e medidas de segurança de acesso à porta I/O para impedir a conexão de dispositivos não autorizados. Você também pode desabilitar portas específicas por meio da configuração de Unified Extensible Firmware Interface (UEFI).

Cada módulo de computação certificado deve ser fornecido com a tecnologia compatível com o Trusted Platform Module (TPM) 2,0 habilitada por padrão. O TPM é usado para criptografar as informações de logon da conta do recurso de salas de equipe.

A inicialização segura é habilitada por padrão. A inicialização segura é um padrão de segurança desenvolvido por membros do setor de PC para ajudar a garantir que um dispositivo seja inicializado usando somente software que seja confiável para o OEM (fabricante original do equipamento). Quando o computador é iniciado, o firmware verifica a assinatura de cada parte do software de inicialização, incluindo drivers de firmware UEFI (também conhecidos como ROMs de opção), aplicativos EFI e o sistema operacional. Se as assinaturas forem válidas, o computador será inicializado e o firmware concederá controle ao sistema operacional. Para obter mais informações, consulte [inicialização segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

O acesso às configurações de UEFI só é possível ao conectar um teclado e um mouse físico. Isso impede que seja capaz de acessar a UEFI por meio do console habilitado para toque em salas de equipe, bem como quaisquer outros monitores habilitados para toque em salas de equipe.

A proteção de DMA (acesso direto à memória) do kernel é uma configuração do Windows 10 habilitada em salas de equipe. Com esse recurso, o sistema operacional e o firmware do sistema protegem o sistema contra ataques de DMA maliciosos e indesejados para todos os dispositivos compatíveis com DMA:

- Durante o processo de inicialização.

- Contra o DMA mal-intencionado por dispositivos conectados a portas com recursos de DMA internos/externos, como M. 2 slots PCIe e Thunderbolt 3, durante o tempo de execução do sistema operacional.

As salas de equipe também habilitam a integridade de código protegida do hipervisor (HVCI). Um dos recursos fornecidos pela HVCI é a proteção de credenciais. A proteção de credenciais oferece os seguintes benefícios:

- **Segurança de hardware** O NTLM, o Kerberos e o Gerenciador de credenciais aproveitam os recursos de segurança da plataforma, incluindo a inicialização e a virtualização seguras, para proteger as credenciais.

- **Segurança baseada em virtualização** As credenciais de NTLM e Kerberos derivadas do Windows e outros segredos são executados em um ambiente protegido que é isolado do sistema operacional em execução.

- **Melhor proteção contra ameaças persistentes avançadas** Quando as credenciais de domínio do Gerenciador de credenciais, NTLM e Kerberos são protegidas usando a segurança baseada em virtualização, as técnicas de ataque e as ferramentas de roubo de credenciais usadas em muitos ataques direcionados são bloqueadas. Malware em execução no sistema operacional com privilégios administrativos não podem extrair segredos protegidos por segurança baseada em virtualização.

## <a name="software-security"></a>Segurança de software

Depois que o Microsoft Windows for inicializado, as salas de equipe entrarão automaticamente em uma conta de usuário local do Windows chamada Skype. A conta do Skype não tem senha. Para tornar a sessão de conta do Skype segura, as etapas a seguir são adotadas.

> [!IMPORTANT]
> Não altere a senha ou edite a conta de usuário do Skype local. Isso pode impedir a entrada de salas de equipe automaticamente.

O aplicativo salas do Microsoft Teams é executado usando o recurso de acesso atribuído encontrado no Windows 10 1903 e posterior. O acesso atribuído é um recurso no Windows 10 que limita os pontos de entrada do aplicativo expostos ao usuário. Isso é o que habilita o modo de quiosque do aplicativo único. Usando o inicializador de Shell, as salas do teams são configuradas como um dispositivo de quiosque que executa um aplicativo da área de trabalho do Windows como a interface O aplicativo salas do Microsoft Teams substitui o shell padrão (explorer.exe) que geralmente é executado quando um usuário faz logon. Em outras palavras, o Shell tradicional do Explorer não é iniciado. Isso reduz bastante a superfície de vulnerabilidade das salas do Microsoft Teams no Windows. Para obter mais informações, consulte [Configurar quiosques e sinais digitais em edições da área de trabalho do Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods).

Se você decidir executar uma verificação de segurança ou um benchmark do centro de segurança da Internet (CIS) nas salas de equipe, a verificação só poderá ser executada sob o contexto de uma conta de administrador local, pois a conta de usuário do Skype não é compatível com a execução de aplicativos que não sejam o aplicativo salas de equipe. Muitos dos recursos de segurança aplicados ao contexto de usuário do Skype não se aplicam a outros usuários locais e, como resultado, essas verificações de segurança não modelarão o bloqueio de segurança completo aplicado à conta do Skype. Portanto, não é recomendável executar uma verificação local em salas de equipe. No entanto, você pode executar testes de penetração externos, se desejado. Por isso, recomendamos que você execute testes de penetração externos em dispositivos de salas de equipe em vez de executar verificações locais.

Além disso, as políticas de bloqueio são aplicadas para limitar os recursos não administrativos a serem usados. Um filtro de teclado está habilitado para interceptar e bloquear combinações de teclado potencialmente inseguras que não são cobertas pelas políticas de acesso atribuídas. Somente os usuários com direitos administrativos locais ou de domínio podem entrar no Windows para gerenciar as salas de equipe. Essas e outras políticas aplicadas ao Windows em dispositivos de salas do Microsoft Teams são continuamente avaliadas e testadas durante o ciclo de vida do produto.

## <a name="account-security"></a>Segurança da conta

Os dispositivos de salas de equipe incluem uma conta administrativa chamada "administrador" com uma senha padrão. É altamente recomendável que você altere a senha padrão assim que possível após a conclusão da instalação.

A conta de administrador não é necessária para a operação adequada dos dispositivos de salas de equipe e pode ser renomeada ou até mesmo excluída. No entanto, antes de excluir a conta de administrador, verifique se você configurou uma conta de administrador local alternativa configurada antes de remover a que vem com dispositivos de salas de equipe. Para saber mais sobre como alterar uma senha de uma conta local do Windows usando as ferramentas internas do Windows ou o PowerShell, confira o seguinte:

- [Alterar ou redefinir sua senha do Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Você também pode importar contas de domínio para o grupo de administradores locais do Windows. Você pode fazer isso para contas do Azure AD usando o Intune. Para obter mais informações, consulte [CSP de políticas – RestrictedGroups.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!CAUTION]
> Se você excluir ou desabilitar a conta de administrador antes de conceder permissões de administrador local para outra conta local ou de domínio, poderá perder a capacidade de administrar o dispositivo de salas de equipe. Se isso acontecer, você precisará redefinir o dispositivo para suas configurações originais e completar o processo de configuração.
>
> Não conceda permissões de administrador local à conta de usuário do Skype.

O designer de configuração do Windows pode ser usado para criar pacotes de provisionamento do Windows 10. Juntamente com a alteração da senha do administrador local, você também pode fazer coisas como alterar o nome da máquina e registrar-se no Azure Active Directory. Para obter mais informações sobre como criar um pacote de provisionamento do designer de configuração do Windows, consulte [pacotes de provisionamento para Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Você precisa criar uma conta de recurso para cada dispositivo de salas de equipe para que ele possa se conectar ao Teams. Você não pode usar a autenticação de dois fatores ou multi fatores com esta conta. Exigir um segundo fator impede que a conta seja capaz de entrar automaticamente no aplicativo salas de equipe após uma reinicialização. No entanto, você pode habilitar a autenticação moderna para obter segurança adicional para esta conta. Além disso, as políticas de acesso condicional com base em localização podem ser implantadas para a conta do recurso para impedir a conexão à conta a partir de um local não aprovado. Para obter mais informações, consulte [usando a condição de localização em uma política de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

Recomendamos que você crie a conta do recurso no Azure AD, se possível. Embora uma conta sincronizada possa funcionar com salas de equipe em implantações híbridas, essas contas sincronizadas muitas vezes têm dificuldade para se conectar a salas de equipe e podem ser difíceis de solucionar o problema. Se você optar por usar um serviço de Federação de terceiros para autenticar as credenciais da conta do recurso, certifique-se de que o IDP secundário responda com o `wsTrustResponse` atributo definido como `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Segurança de rede

Geralmente, as salas de equipe têm os mesmos requisitos de rede que qualquer cliente do Microsoft Teams. O acesso por meio de firewalls e outros dispositivos de segurança é o mesmo para salas de equipe para qualquer outro cliente do Microsoft Teams. Especificamente para salas de equipe, as categorias listadas como "obrigatórias" para equipes devem estar abertas no firewall. As salas de equipe também precisam ter acesso ao Windows Update, à Microsoft Store e ao Microsoft Intune (se você usar o Microsoft Intune para gerenciar seus dispositivos). Para obter a lista completa de IPs e URLs necessárias para as salas do Microsoft Teams, consulte:

- [URLs e intervalos de endereços IP](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams) **do Microsoft teams** Office 365
- **Windows Update** [Configurar o WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
-  [Pré-requisitos da Microsoft Store para a Microsoft Store para empresas e instituições de ensino](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- Pontos de rede do **Microsoft Intune** [para Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Se você estiver usando o componente de serviços gerenciados de salas do Microsoft Teams Premium, também será necessário garantir que as salas de equipe possam acessar as seguintes URLs:

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

As salas de equipe são configuradas para manter-se atualizado automaticamente com as atualizações mais recentes do Windows, incluindo atualizações de segurança. Salas de equipe instala todas as atualizações pendentes todos os dias a partir de 2:00am usando uma política local predefinida. Não é necessário usar ferramentas adicionais para implantar e aplicar atualizações do Windows. Usar ferramentas adicionais para implantar e aplicar atualizações pode atrasar a instalação de correções do Windows e, assim, levar a uma implantação menos segura. O aplicativo salas de equipe é implantado usando a Microsoft Store. Se seus dispositivos estão licenciados com o padrão de salas do Microsoft Teams, todas as novas versões do aplicativo são instaladas automaticamente durante o processo de correção noturna. Se seus dispositivos estão licenciados com as salas do Microsoft Teams Premium e registrados no serviço Microsoft Managed, novas versões do aplicativo salas de equipe são instaladas por seu plano de distribuição definido.

Os dispositivos de salas de equipe funcionam com a maioria da 802.1 X ou outros protocolos de segurança baseados em rede. No entanto, não podemos testar as salas de equipe em relação a todas as configurações de segurança de rede possíveis. Portanto, se surgirem problemas de desempenho que possam ser rastreados para problemas de desempenho de rede, talvez seja necessário desabilitar esses protocolos se eles estiverem configurados em sua organização.

Para obter o melhor desempenho da mídia em tempo real, recomendamos que você configure o tráfego de mídia do teams para ignorar servidores proxy e outros dispositivos de segurança de rede. A mídia em tempo real é um grande diferencial de latência e servidores proxy, e os dispositivos de segurança de rede podem degradar significativamente a qualidade de vídeo e áudio do usuário. Além disso, como a mídia de equipes já está criptografada, não há um benefício tangível de passar o tráfego por meio de um servidor proxy. Para obter mais informações, consulte [rede para cima (para a nuvem), ponto de vista de um arquiteto](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) que discute recomendações de rede para melhorar o desempenho de mídia com o Microsoft Teams e salas do Microsoft Teams.

> [!IMPORTANT]
> As salas de equipe não dão suporte a servidores proxy autenticados.

Os dispositivos de salas de equipe não precisam se conectar a uma LAN interna. Considere a possibilidade de colocar salas de equipe em um segmento de rede seguro com acesso direto à Internet. Se a sua LAN interna ficar comprometida, as oportunidades do vetor de ataque em relação às salas de equipe serão reduzidas.

É altamente recomendável que você conecte seus dispositivos de salas de equipe a uma rede com fio. O uso de redes sem fio em dispositivos de salas de equipe não é recomendado nem certificado. Alguns recursos de conectividade, como Wi-Fi senso, são desativados por padrão.

Junção de proximidade e outras salas de equipe os recursos dependem do Bluetooth. No entanto, a implementação do Bluetooth em dispositivos de salas de equipe não permite uma conexão de dispositivo externo a um dispositivo de salas de equipe. A tecnologia Bluetooth uso em dispositivos de salas de equipe está atualmente limitada a beacons de publicidade e proximal solicitações de conexão. O `ADV_NONCONN_INT` tipo de unidade de dados de protocolo (PDU) é usado no Beacon de publicidade. Esse tipo de PDU destina-se a dispositivos que não são conectáveis a divulgação de informações para o dispositivo de escuta. Não há dispositivo Bluetooth emparelhando como parte desses recursos. Detalhes adicionais sobre protocolos Bluetooth podem ser encontrados no [site Bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
