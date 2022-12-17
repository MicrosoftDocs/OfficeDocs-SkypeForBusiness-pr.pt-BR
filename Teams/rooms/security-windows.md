---
title: Salas do Microsoft Teams na segurança do Windows
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
description: Saiba como proteger seu Salas do Microsoft Teams em dispositivos Windows.
ms.openlocfilehash: f7774b43542885118bd66eb09cf1d30049b84425
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438466"
---
# <a name="microsoft-teams-rooms-on-windows-security"></a>Salas do Microsoft Teams na segurança do Windows

Microsoft trabalha com nossos parceiros para fornecer uma solução segura e não requer ações adicionais para proteger Salas do Microsoft Teams no Windows. Este artigo discute muitos dos recursos de segurança encontrados em Salas do Teams no Windows.

Para obter informações sobre segurança em Salas do Teams em dispositivos Android, consulte [Salas do Microsoft Teams na segurança do Android](security-android.md).

> [!NOTE]
> Salas do Microsoft Teams não deve ser tratado como uma estação de trabalho típica do usuário final. Não só os casos de uso são muito diferentes, mas os perfis de segurança padrão também são muito diferentes.
> Este artigo se aplica a Salas do Microsoft Teams dispositivos em execução no Windows.

Os dados limitados do usuário final são armazenados em Salas do Teams. Os dados do usuário final podem ser armazenados nos arquivos de log apenas para solução de problemas e suporte. Em nenhum momento um participante de uma reunião pode usar Salas do Teams copiar arquivos para o disco rígido ou entrar como eles mesmos. Nenhum dado do usuário final é transferido ou acessível pelo dispositivo Salas do Microsoft Teams.

Mesmo que os usuários finais não possam colocar arquivos em um disco rígido Salas do Teams, Microsoft Defender ainda está habilitado. Salas do Teams desempenho é testado com Microsoft Defender. Desabilitar esse ou adicionar software de segurança de ponto de extremidade pode levar a resultados imprevisíveis e potencial degradação do sistema.

## <a name="hardware-security"></a>Segurança de hardware

Em um ambiente Salas do Teams, há um módulo de computação central que executa Windows 10 IoT Enterprise edição. Cada módulo de computação certificado deve ter uma solução de montagem segura, um slot de bloqueio de segurança (por exemplo, bloqueio kensington) e medidas de segurança de acesso à porta de E/S para impedir a conexão de dispositivos não autorizados. Você também pode desabilitar portas específicas por meio da configuração UEFI (Unified Extensible Firmware Interface).

Cada módulo de computação certificado deve ser enviado com a tecnologia compatível com o TPM (Trusted Platform Module) 2.0 habilitada por padrão. O TPM é usado para criptografar as informações de logon da conta de recursos Salas do Teams.

A inicialização segura está habilitada por padrão. A inicialização segura é um padrão de segurança desenvolvido por membros da indústria de computadores para ajudar a garantir que um dispositivo inicialize usando apenas software confiável pelo OEM (Fabricante de Equipamentos Original). Quando o computador é iniciado, o firmware verifica a assinatura de cada parte do software de inicialização, incluindo drivers de firmware UEFI (também conhecidos como ROMs de opção), aplicativos EFI e o sistema operacional. Se as assinaturas forem válidas, o computador será inicializado e o firmware fornecerá controle ao sistema operacional. Para obter mais informações, confira [Inicialização segura](/windows-hardware/design/device-experiences/oem-secure-boot).

O acesso às configurações UEFI só é possível anexando um teclado físico e um mouse. Isso impede que seja possível acessar o UEFI por meio do console habilitado para toque Salas do Teams, bem como quaisquer outras exibições habilitadas para toque anexadas a Salas do Teams.

O Kernel Direct Memory Access (DMA) Protection é uma configuração de Windows 10 habilitada no Salas do Teams. Com esse recurso, o sistema operacional e o firmware do sistema protegem o sistema contra ataques DMA mal-intencionados e não intencionais para todos os dispositivos capazes de DMA:

- Durante o processo de inicialização.

- Contra DMA mal-intencionado por dispositivos conectados a portas internas/externas com capacidade de DMA facilmente acessíveis, como slots M.2 PCIe e Thunderbolt 3, durante o runtime do sistema operacional.

Salas do Teams também habilita a HVCI (integridade de código protegida pelo Hypervisor). Um dos recursos fornecidos pelo HVCI é o Credential Guard. O Credential Guard fornece os seguintes benefícios:

- **Segurança de hardware** NTLM, Kerberos e Credential Manager aproveitam os recursos de segurança da plataforma, incluindo Inicialização Segura e virtualização, para proteger credenciais.

- **Segurança baseada em virtualização** As credenciais derivadas do Windows NTLM e Kerberos e outros segredos são executados em um ambiente protegido isolado do sistema operacional em execução.

- **Melhor proteção contra ameaças persistentes avançadas** Quando as credenciais de domínio do Credential Manager, as credenciais derivadas de NTLM e Kerberos são protegidas usando segurança baseada em virtualização, as técnicas de ataque de roubo de credencial e as ferramentas usadas em muitos ataques de destino são bloqueadas. O malware em execução no sistema operacional com privilégios administrativos não pode extrair segredos protegidos pela segurança baseada em virtualização.

## <a name="software-security"></a>Segurança de Software

Depois de Microsoft botas windows, Salas do Teams entra automaticamente em uma conta de usuário local do Windows chamada Skype. A conta do Skype não tem senha. Para tornar a sessão da conta do Skype segura, as etapas a seguir são tomadas.

> [!IMPORTANT]
> Não altere a senha nem edite a conta de usuário local do Skype. Isso pode impedir que Salas do Teams entrem automaticamente.

O aplicativo Salas do Microsoft Teams é executado usando o recurso acesso atribuído encontrado no Windows 10 1903 e posterior. O Acesso Atribuído é um recurso no Windows 10 que limita os pontos de entrada do aplicativo expostos ao usuário. Isso é o que habilita o modo de quiosque de aplicativo único. Usando o Shell Launcher, Salas do Teams é configurado como um dispositivo de quiosque que executa um aplicativo de área de trabalho do Windows como a interface do usuário. O aplicativo Salas do Microsoft Teams substitui o shell padrão (explorer.exe) que geralmente é executado quando um usuário faz logon. Em outras palavras, o shell do Explorer tradicional não é iniciado. Isso reduz consideravelmente a Salas do Microsoft Teams superfície de vulnerabilidade no Windows. Para obter mais informações, consulte [Configurar quiosques e sinais digitais em edições da área de trabalho do Windows](/windows/configuration/kiosk-methods).

Se você decidir executar uma verificação de segurança ou um benchmark do CIS (Center for Internet Security) no Salas do Teams, a verificação só poderá ser executada no contexto de uma conta de administrador local, pois a conta de usuário do Skype não dá suporte à execução de aplicativos que não sejam o aplicativo Salas do Teams. Muitos dos recursos de segurança aplicados ao contexto de usuário do Skype não se aplicam a outros usuários locais e, como resultado, essas verificações de segurança não aparecerão no bloqueio de segurança completo aplicado à conta do Skype. Portanto, não é recomendável executar uma verificação local no Salas do Teams. No entanto, você pode executar testes de penetração externa, se assim desejar. Por causa disso, recomendamos que você execute testes de penetração externa em dispositivos Salas do Teams em vez de executar verificações locais.

Além disso, as políticas de bloqueio são aplicadas para limitar o uso de recursos não administrativos. Um filtro de teclado está habilitado para interceptar e bloquear combinações de teclado potencialmente inseguras que não são cobertas por políticas de Acesso Atribuído. Somente usuários com direitos administrativos locais ou de domínio podem entrar no Windows para gerenciar Salas do Teams. Essas e outras políticas aplicadas ao Windows em dispositivos Salas do Microsoft Teams são continuamente avaliadas e testadas durante o ciclo de vida do produto.

## <a name="account-security"></a>Segurança da Conta

Salas do Teams dispositivos incluem uma conta administrativa chamada "Administração" com uma senha padrão. Recomendamos que você altere a senha padrão o mais rápido possível depois de concluir a instalação.

A conta Administração não é necessária para a operação adequada de dispositivos Salas do Teams e pode ser renomeada ou até mesmo excluída. No entanto, antes de excluir a conta Administração, certifique-se de configurar uma conta de administrador local alternativa configurada antes de remover a que é enviada com dispositivos Salas do Teams. Para obter mais informações sobre como alterar uma senha para uma conta local do Windows usando ferramentas internas do Windows ou PowerShell, confira o seguinte:

- [Alterar ou redefinir sua senha do Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser#example-2--change-the-password-on-an-account)

Você também pode importar contas de domínio para o grupo de administradores do Windows local. Você pode fazer isso para contas Azure AD usando Intune. Para obter mais informações, consulte [Política CSP – RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!NOTE]
> Se você estiver usando consoles do Crestron, atualize também a senha Administração no console, bem como no módulo de computação. Para obter mais informações, entre em contato com Crestron.

> [!CAUTION]
> Se você excluir ou desabilitar a conta Administração antes de conceder permissões de administrador local a outra conta local ou de domínio, poderá perder a capacidade de administrar o dispositivo Salas do Teams. Se isso acontecer, você precisará redefinir o dispositivo de volta para suas configurações originais e concluir o processo de instalação novamente.

Não conceda permissões de administrador local à conta de usuário do Skype.

O Designer de Configuração do Windows pode ser usado para criar pacotes de provisionamento Windows 10. Além de alterar a senha do Administração local, você também pode fazer coisas como alterar o nome do computador e se registrar no Azure Active Directory. Para obter mais informações sobre como criar um pacote de provisionamento do Designer de Configuração do Windows, consulte [Provisionamento de pacotes para Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

Você precisa criar uma conta de recurso para cada Salas do Teams dispositivo para que ele possa entrar no Teams. Você não pode usar a autenticação de dois fatores ou multifator com essa conta. Exigir um segundo fator impediria que a conta pudesse entrar automaticamente no aplicativo Salas do Teams após uma reinicialização. No entanto, você pode habilitar a Autenticação Moderna para segurança adicional para essa conta. Além disso, as políticas de Acesso Condicional do Azure Active Directory e Intune Políticas de Conformidade podem ser implantadas para proteger a conta de recursos. Para obter mais informações, consulte [Acesso condicional com suporte e Intune políticas de conformidade do dispositivo para Salas do Microsoft Teams](supported-ca-and-compliance-policies.md) e [acesso condicional e conformidade Intune para Salas do Microsoft Teams](conditional-access-and-compliance-for-devices.md)

Recomendamos que você crie a conta de recursos no Azure AD, se possível. Embora uma conta sincronizada possa funcionar com Salas do Teams em implantações híbridas, essas contas sincronizadas geralmente têm dificuldade para entrar em Salas do Teams e podem ser difíceis de solucionar problemas. Se você optar por usar um serviço de federação de terceiros para autenticar as credenciais da conta de recurso, verifique se o IDP de terceiros responde com o `wsTrustResponse` atributo definido como `urn:oasis:names:tc:SAML:1.0:assertion`.

## <a name="network-security"></a>Segurança de Rede

Geralmente, Salas do Teams tem os mesmos requisitos de rede que qualquer cliente Microsoft Teams. O acesso por meio de firewalls e outros dispositivos de segurança é o mesmo para Salas do Teams que para qualquer outro cliente Microsoft Teams. Específicas para Salas do Teams, as categorias listadas como "necessárias" para o Teams devem estar abertas no firewall. Salas do Teams também precisa de acesso a Windows Update, Microsoft Store e Microsoft Intune (se você usar Microsoft Intune para gerenciar seus dispositivos). Para obter a lista completa de IPs e URLs necessárias para Salas do Microsoft Teams, consulte:

-  [urls de Office 365 do Teams Microsoft e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [configurar o WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- Pré-requisitos da **Loja Microsoft** [para Microsoft Store para Empresas e Educação](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [pontos de extremidade de rede para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Se você estiver usando o componente Salas do Microsoft Teams serviços gerenciados do Salas Microsoft Teams Pro, também precisará garantir que Salas do Teams possa acessar as seguintes URLs:

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

Salas do Teams está configurado para se manter automaticamente corrigido com as atualizações mais recentes do Windows, incluindo atualizações de segurança. Salas do Teams instala todas as atualizações pendentes todos os dias a partir das 2h usando uma política local pré-definida. Não é necessário usar ferramentas adicionais para implantar e aplicar Atualizações do Windows. O uso de ferramentas adicionais para implantar e aplicar atualizações pode atrasar a instalação de patches do Windows e, portanto, levar a uma implantação menos segura. O aplicativo Salas do Teams é implantado usando a Microsoft Store.

<!-- LICENSE-REVIEW If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process. If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan. -->

Salas do Teams dispositivos funcionam com a maioria dos protocolos de segurança baseados em rede 802.1X ou outros. No entanto, não podemos testar Salas do Teams em todas as configurações de segurança de rede possíveis. Portanto, se surgirem problemas de desempenho que podem ser rastreados para problemas de desempenho de rede, talvez seja necessário desabilitar esses protocolos se eles estiverem configurados em sua organização.

Para o melhor desempenho da mídia em tempo real, recomendamos que você configure o tráfego de mídia do Teams para ignorar servidores proxy e outros dispositivos de segurança de rede. A mídia em tempo real é muito sensível à latência e servidores proxy e dispositivos de segurança de rede podem degradar significativamente a qualidade de vídeo e áudio dos usuários. Além disso, como a mídia do Teams já está criptografada, não há nenhum benefício tangível de passar o tráfego por meio de um servidor proxy. Para obter mais informações, consulte [Networking up (para a nuvem) – Um ponto de vista do arquiteto](/microsoft-365/solutions/networking-design-principles) que discute recomendações de rede para melhorar o desempenho da mídia com Microsoft Teams e Salas do Microsoft Teams.

> [!IMPORTANT]
> Salas do Teams não dá suporte a servidores proxy autenticados.

Salas do Teams dispositivos não precisam se conectar a uma LAN interna. Considere colocar Salas do Teams em um segmento de rede seguro com acesso direto à Internet. Se sua LAN interna ficar comprometida, as oportunidades de vetor de ataque para Salas do Teams serão reduzidas.

Recomendamos fortemente que você conecte seus dispositivos Salas do Teams a uma rede com fio. O uso de redes sem fio em dispositivos Salas do Teams não é recomendado ou certificado. Alguns recursos de conectividade, como Wi-Fi Sense, são desabilitados por padrão.

A junção de proximidade e outros recursos Salas do Teams dependem do Bluetooth. No entanto, a implementação bluetooth em dispositivos Salas do Teams não permite uma conexão de dispositivo externo com um dispositivo Salas do Teams. O uso de tecnologia Bluetooth em dispositivos Salas do Teams atualmente está limitado a sinalizadores de publicidade e conexões proximal solicitadas. O `ADV_NONCONN_INT` tipo PDU (unidade de dados de protocolo) é usado no sinalizador de publicidade. Esse tipo de PDU é para dispositivos não conectáveis que anunciam informações para o dispositivo ouvinte. Não há emparelhamento de dispositivo Bluetooth como parte desses recursos. Detalhes adicionais sobre protocolos Bluetooth podem ser encontrados no [site do SIG Bluetooth](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
