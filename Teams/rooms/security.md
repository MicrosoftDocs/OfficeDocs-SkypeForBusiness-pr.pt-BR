---
title: Salas do Microsoft Teams segurança
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
description: Saiba como proteger seus dispositivos Salas do Microsoft Teams segurança.
ms.openlocfilehash: 231039324e15afb7b24f194623e54455d51e85c2
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606210"
---
# <a name="microsoft-teams-rooms-security"></a>Salas do Microsoft Teams segurança

A Microsoft trabalha com nossos parceiros para fornecer uma solução segura e que não exige ações adicionais para proteger Salas do Microsoft Teams. Este artigo aborda muitos dos recursos de segurança encontrados no Salas do Teams.

> [!NOTE]
> Salas do Microsoft Teams deve ser tratado como uma estação de trabalho típica do usuário final. Não apenas os casos de uso são muito diferentes, mas os perfis de segurança padrão também são muito diferentes.
> Este artigo se aplica a Salas do Microsoft Teams dispositivos em execução no Windows.

Dados limitados do usuário final são armazenados Salas do Teams. Os dados do usuário final podem ser armazenados nos arquivos de log apenas para solução de problemas e suporte. Em nenhum momento, um participante de uma reunião pode Salas do Teams copiar arquivos para o disco rígido ou entrar como eles mesmos. Nenhum dado do usuário final é transferido ou acessível pelo Salas do Microsoft Teams dispositivo.

Embora os usuários finais não possam colocar arquivos em um disco Salas do Teams disco rígido, o Microsoft Defender ainda está habilitado. Salas do Teams desempenho é testado com o Microsoft Defender. Desabilitar isso ou adicionar software de segurança de ponto de extremidade pode levar a resultados imprevisíveis e potencial degradação do sistema.

## <a name="hardware-security"></a>Segurança de hardware

Em um Salas do Teams, há um módulo de computação central que executa Windows 10 IoT Enterprise edição. Cada módulo de computação certificado deve ter uma solução de montagem segura, um slot de bloqueio de segurança (por exemplo, bloqueio kensington) e medidas de segurança de acesso à porta de E/S para impedir a conexão de dispositivos não autorizados. Você também pode desabilitar portas específicas por meio da configuração UEFI (Unified Extensible Firmware Interface).

Cada módulo de computação certificado deve ser fornecido com a tecnologia compatível com o TPM (Trusted Platform Module) 2.0 habilitada por padrão. O TPM é usado para criptografar as informações de logon para a Salas do Teams de recursos.

A inicialização segura é habilitada por padrão. A inicialização segura é um padrão de segurança desenvolvido por membros do setor de computadores para ajudar a garantir que um dispositivo seja inicializado usando apenas softwares confiáveis pelo OEM (Fabricante de Equipamento Original). Quando o computador é iniciado, o firmware verifica a assinatura de cada parte do software de inicialização, incluindo drivers de firmware UEFI (também conhecidos como ROMs de opção), aplicativos EFI e o sistema operacional. Se as assinaturas forem válidas, o computador será inicializado e o firmware dará controle ao sistema operacional. Para obter mais informações, consulte [Inicialização segura](/windows-hardware/design/device-experiences/oem-secure-boot).

O acesso às configurações de UEFI só é possível anexando um teclado físico e um mouse. Isso impede a capacidade de acessar a UEFI por meio Salas do Teams console habilitado para toque, bem como quaisquer outras exibições habilitadas para toque anexadas ao Salas do Teams.

A Proteção contra DMA (Acesso Direto à Memória) do Kernel é Windows 10 configuração que está habilitada no Salas do Teams. Com esse recurso, o sistema operacional e o firmware do sistema protegem o sistema contra ataques de AMD mal-intencionados e indesejados para todos os dispositivos compatíveis com AMD:

- Durante o processo de inicialização.

- Em relação ao AMD mal-intencionado por dispositivos conectados a portas compatíveis com DMA internas/externas facilmente acessíveis, como slots PCIe M.2 e Thunderbolt 3, durante o runtime do sistema operacional.

Salas do Teams também habilita a HVCI (integridade de código protegida por hipervisor). Um dos recursos fornecidos pelo HVCI é o Credential Guard. O Credential Guard oferece os seguintes benefícios:

- **Segurança de hardware** O NTLM, o Kerberos e o Gerenciador de Credenciais aproveitam os recursos de segurança da plataforma, incluindo Inicialização Segura e virtualização, para proteger as credenciais.

- **Segurança baseada em virtualização** As credenciais derivadas de NTLM e Kerberos do Windows e outros segredos são executadas em um ambiente protegido isolado do sistema operacional em execução.

- **Melhor proteção contra ameaças persistentes avançadas** Quando credenciais de domínio do Gerenciador de Credenciais, NTLM e credenciais derivadas de Kerberos são protegidas usando a segurança baseada em virtualização, as técnicas de ataque de roubo de credenciais e as ferramentas usadas em muitos ataques direcionados são bloqueadas. Malware em execução no sistema operacional com privilégios administrativos não pode extrair segredos protegidos pela segurança baseada em virtualização.

## <a name="software-security"></a>Segurança de software

Após a inicialização do Microsoft Windows, Salas do Teams automaticamente entra em uma conta de usuário local do Windows chamada Skype. A conta do Skype não tem senha. Para tornar a sessão da conta do Skype segura, as etapas a seguir são executadas.

> [!IMPORTANT]
> Não altere a senha nem edite a conta de usuário local do Skype. Isso pode impedir que Salas do Teams entre automaticamente.

O Salas do Microsoft Teams aplicativo é executado usando o recurso Acesso Atribuído encontrado no Windows 10 1903 e posterior. O Acesso Atribuído é um recurso no Windows 10 que limita os pontos de entrada do aplicativo expostos ao usuário. Isso é o que habilita o modo de quiosque de aplicativo único. Usando o Iniciador de Shell, Salas do Teams é configurado como um dispositivo de quiosque que executa um aplicativo da área de trabalho do Windows como a interface do usuário. O Salas do Microsoft Teams substitui o shell padrão (explorer.exe) que geralmente é executado quando um usuário faz logon. Em outras palavras, o shell tradicional do Explorer não é iniciado. Isso reduz consideravelmente a superfície Salas do Microsoft Teams vulnerabilidade no Windows. Para obter mais informações, consulte [Configurar quiosques e sinais digitais em edições da área de trabalho do Windows](/windows/configuration/kiosk-methods).

Se você decidir executar uma verificação de segurança ou um parâmetro de comparação do CIS (Center for Internet Security) no Salas do Teams, a verificação só poderá ser executada no contexto de uma conta de administrador local, pois a conta de usuário do Skype não dá suporte à execução de aplicativos diferentes do aplicativo Salas do Teams. Muitos dos recursos de segurança aplicados ao contexto de usuário do Skype não se aplicam a outros usuários locais e, como resultado, essas verificações de segurança não exibirão o bloqueio de segurança completo aplicado à conta do Skype. Portanto, não é recomendável executar uma verificação local no Salas do Teams. No entanto, você pode executar testes de penetração externos, se assim desejar. Por isso, recomendamos que você execute testes de penetração externos em Salas do Teams em vez de executar verificações locais.

Além disso, as políticas de bloqueio são aplicadas para limitar o uso de recursos não administrativos. Um filtro de teclado está habilitado para interceptar e bloquear combinações de teclado potencialmente inseguras que não são cobertas pelas políticas de Acesso Atribuído. Somente usuários com direitos administrativos locais ou de domínio têm permissão para entrar no Windows para gerenciar Salas do Teams. Essas e outras políticas aplicadas ao Windows Salas do Microsoft Teams dispositivos são continuamente avaliadas e testadas durante o ciclo de vida do produto.

## <a name="account-security"></a>Segurança da Conta

Salas do Teams dispositivos incluem uma conta administrativa chamada "Administração" com uma senha padrão. É altamente recomendável que você altere a senha padrão assim que possível após concluir a configuração.

A Administração não é necessária para a operação adequada de dispositivos Salas do Teams e pode ser renomeada ou até mesmo excluída. No entanto, antes de excluir a Administração, verifique se você configurou uma conta de administrador local alternativa configurada antes de remover aquela fornecida com Salas do Teams dispositivos. Para obter mais informações sobre como alterar uma senha para uma conta local do Windows usando ferramentas internas do Windows ou o PowerShell, consulte o seguinte:

- [Alterar ou redefinir sua senha do Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser#example-2--change-the-password-on-an-account)

Você também pode importar contas de domínio para o grupo local de Administradores do Windows. Você pode fazer isso para Azure AD contas usando Intune. Para obter mais informações, consulte [CSP de política – RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!NOTE]
> Se você estiver usando consoles crestron, certifique-se de também atualizar a senha Administração no console, bem como no módulo de computação. Para obter mais informações, entre em contato com a Crestron.

> [!CAUTION]
> Se você excluir ou desabilitar a conta Administração antes de conceder permissões de Administrador local a outra conta local ou de domínio, poderá perder a capacidade de administrar o Salas do Teams local. Se isso acontecer, você precisará redefinir o dispositivo de volta para suas configurações originais e concluir o processo de instalação novamente.

Não conceda permissões de Administrador local à conta de usuário do Skype.

O Designer de Configuração do Windows pode ser usado para criar Windows 10 de provisionamento. Além de alterar a senha Administração local, você também pode fazer coisas como alterar o nome do computador e registrar-se no Azure Active Directory. Para obter mais informações sobre como criar um pacote de provisionamento do Designer de Configuração do Windows, consulte [Pacotes de provisionamento para Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

Você precisa criar uma conta de recurso para cada dispositivo Salas do Teams para que ele possa entrar no Teams. Você não pode usar a autenticação multifator ou de dois fatores com essa conta. Exigir um segundo fator impediria que a conta fosse capaz de entrar automaticamente no aplicativo Salas do Teams após uma reinicialização. No entanto, você pode habilitar a Autenticação Moderna para segurança adicional para essa conta. Além disso, as políticas de Acesso Condicional do Azure Active Directory e as Intune de Conformidade podem ser implantadas para proteger a conta de recurso. Para obter mais informações, consulte Acesso Condicional e políticas de conformidade do dispositivo [Intune](supported-ca-and-compliance-policies.md) com suporte para Salas do Microsoft Teams e acesso condicional e conformidade [Intune para](conditional-access-and-compliance-for-devices.md) Salas do Microsoft Teams

Recomendamos que você crie a conta de recurso Azure AD, se possível. Embora uma conta sincronizada possa funcionar com Salas do Teams implantações híbridas, essas contas sincronizadas geralmente têm dificuldade para entrar no Salas do Teams e podem ser difíceis de solucionar problemas. Se você optar por usar um serviço de federação de terceiros para autenticar as credenciais da conta de recurso, verifique se o IDP `wsTrustResponse` de terceiros responde com o atributo definido como `urn:oasis:names:tc:SAML:1.0:assertion`.

## <a name="network-security"></a>Segurança de rede

Em geral, Salas do Teams tem os mesmos requisitos de rede que qualquer cliente do Microsoft Teams. O acesso por meio de firewalls e outros dispositivos de segurança é o mesmo Salas do Teams para qualquer outro cliente do Microsoft Teams. Específicas Salas do Teams, as categorias listadas como "obrigatórias" para o Teams devem estar abertas no firewall. Salas do Teams também precisa de acesso Windows Update, Microsoft Store e Microsoft Intune (se você usar Microsoft Intune para gerenciar seus dispositivos). Para obter a lista completa de IPs e URLs necessários para Salas do Microsoft Teams, consulte:

- **Intervalos de** [endereços IP e URLs](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) do Microsoft Teams Office 365
- **Windows Update** [configurar o WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Pré-requisitos da Microsoft Store** [para Microsoft Store para Empresas e Educação](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [de extremidade de rede para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Se você estiver usando o Salas do Microsoft Teams de serviços gerenciados do Salas do Microsoft Teams Pro, também precisará verificar se o Salas do Teams pode acessar as seguintes URLs:

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Salas do Teams é configurado para se manter automaticamente corrigido com as atualizações mais recentes do Windows, incluindo atualizações de segurança. Salas do Teams instala todas as atualizações pendentes todos os dias a partir das 2h usando uma política local predefinido. Não é necessário usar ferramentas adicionais para implantar e aplicar o Windows Atualizações. O uso de ferramentas adicionais para implantar e aplicar atualizações pode atrasar a instalação de patches do Windows e, portanto, levar a uma implantação menos segura. O Salas do Teams aplicativo é implantado usando a Microsoft Store.

<!-- LICENSE-REVIEW If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process. If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan. -->

Salas do Teams dispositivos funcionam com a maioria dos protocolos de segurança baseados em rede ou 802.1X. No entanto, não podemos testar o Salas do Teams todas as configurações de segurança de rede possíveis. Portanto, se surgirem problemas de desempenho que podem ser rastreados para problemas de desempenho de rede, talvez seja necessário desabilitar esses protocolos se eles estiverem configurados em sua organização.

Para obter um desempenho ideal de mídia em tempo real, é altamente recomendável configurar o tráfego de mídia do Teams para ignorar servidores proxy e outros dispositivos de segurança de rede. A mídia em tempo real é sensível à latência, e os servidores proxy e os dispositivos de segurança de rede podem degradar significativamente a qualidade de áudio e vídeo dos usuários. Além disso, como a mídia do Teams já está criptografada, não há nenhum benefício tangível de passar o tráfego por meio de um servidor proxy. Para obter mais informações, consulte Rede até (para a nuvem[) —](/microsoft-365/solutions/networking-design-principles) Ponto de vista de um arquiteto que discute as recomendações de rede para melhorar o desempenho da mídia com o Microsoft Teams e o Salas do Microsoft Teams.

> [!IMPORTANT]
> Salas do Teams não dá suporte a servidores proxy autenticados.

Salas do Teams dispositivos não precisam se conectar a uma LAN interna. Considere colocar o Salas do Teams em um segmento de rede seguro com acesso direto à Internet. Se sua LAN interna for comprometida, as oportunidades de vetor de ataque para Salas do Teams serão reduzidas.

É altamente recomendável que você conecte seus dispositivos Salas do Teams a uma rede com fio. O uso de redes sem fio Salas do Teams dispositivos não é recomendado ou certificado. Alguns recursos de conectividade, como o Wi-Fi Sense, são desabilitados por padrão.

O Ingresso por Proximidade e outros Salas do Teams recursos dependem do Bluetooth. No entanto, a implementação de Bluetooth Salas do Teams dispositivos não permite uma conexão de dispositivo externo com um Salas do Teams dispositivo. O uso da tecnologia Bluetooth Salas do Teams dispositivos está limitado atualmente a sinalizadores de publicidade e conexões de bluetooth solicitadas. O `ADV_NONCONN_INT` tipo de PDU (unidade de dados de protocolo) é usado no sinalizador de publicidade. Esse tipo de PDU é para dispositivos não conectáveis que anunciam informações para o dispositivo de escuta. Não há emparelhamento de dispositivo Bluetooth como parte desses recursos. Detalhes adicionais sobre protocolos Bluetooth podem ser encontrados no site [do Bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
