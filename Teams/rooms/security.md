---
title: Salas do Microsoft Teams Segurança
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
description: Saiba como proteger seus dispositivos Salas do Microsoft Teams segurança.
ms.openlocfilehash: ff5d79b02669f8b3da71396c2bd1eb2348575cf3
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824579"
---
# <a name="microsoft-teams-rooms-security"></a>Salas do Microsoft Teams Segurança

A Microsoft trabalha com nossos parceiros para fornecer uma solução segura e que não exige ações adicionais para proteger Salas do Microsoft Teams. Este artigo aborda muitos dos recursos de segurança encontrados no Salas do Teams.

> [!NOTE]
> Salas do Microsoft Teams deve ser tratado como uma estação de trabalho típica do usuário final. Não apenas os casos de uso são muito diferentes, mas os perfis de segurança padrão também são muito diferentes.
> Este artigo se aplica a Salas do Microsoft Teams dispositivos em execução em Windows.

Dados limitados do usuário final são armazenados em Salas do Teams. Os dados do usuário final podem ser armazenados nos arquivos de log apenas para solução de problemas e suporte. Em nenhum momento, um participante de uma reunião pode Salas do Teams copiar arquivos no disco rígido ou entrar como eles mesmos. Nenhum dado do usuário final é transferido ou acessado pelo dispositivo Salas do Microsoft Teams usuário.

Mesmo que os usuários finais não possam colocar arquivos em um Salas do Teams disco rígido, o Microsoft Defender ainda está habilitado. Salas do Teams desempenho é testado com o Microsoft Defender. Desabilitar isso ou adicionar software de segurança de ponto de extremidade pode levar a resultados imprevisíveis e degradação potencial do sistema.

## <a name="hardware-security"></a>Segurança de hardware

Em um Salas do Teams, há um módulo de computação central que executa Windows 10 IoT Enterprise edição. Cada módulo de computação certificado deve ter uma solução de montagem segura, um slot de bloqueio de segurança (por exemplo, bloqueio kensington) e medidas de segurança de acesso de porta de E/S para impedir a conexão de dispositivos não autorizados. Você também pode desabilitar portas específicas por meio da configuração UEFI (Interface de Firmware Extensível Unificada).

Todos os módulos de computação certificados devem ser comunicados com a tecnologia compatível com o TPM (Trusted Platform Module) 2.0 habilitada por padrão. O TPM é usado para criptografar as informações de logon para a Salas do Teams de recursos.

A inicialização segura é habilitada por padrão. A inicialização segura é um padrão de segurança desenvolvido por membros do setor de computadores para ajudar a garantir que um dispositivo seja inicializado usando apenas o software confiável pelo Fabricante de Equipamento Original (OEM). Quando o computador é iniciado, o firmware verifica a assinatura de cada parte do software de inicialização, incluindo drivers de firmware UEFI (também conhecidos como ROMs de opção), aplicativos EFI e o sistema operacional. Se as assinaturas são válidas, o computador é inicializado e o firmware dá controle ao sistema operacional. Para obter mais informações, consulte [Inicialização segura](/windows-hardware/design/device-experiences/oem-secure-boot).

O acesso às configurações uefi só é possível anexando um teclado físico e um mouse. Isso impede que seja possível acessar a UEFI por meio do console Salas do Teams habilitado para toque, bem como qualquer outra exibição habilitada para toque anexada ao Salas do Teams.

A Proteção de Acesso direto à Memória (DMA) do Kernel é uma configuração Windows 10 que está habilitada no Salas do Teams. Com esse recurso, o sistema operacional e o firmware do sistema protegem o sistema contra ataques DMA mal-intencionados e não intencionais para todos os dispositivos compatíveis com DMA:

- Durante o processo de inicialização.

- Em relação ao DMA mal-intencionado por dispositivos conectados a portas internas/externas com capacidade para DMA facilmente acessíveis, como slots PCIe M.2 e Thunderbolt 3, durante o tempo de execução do sistema operacional.

Salas do Teams também habilita a integridade de código protegido pelo Hypervisor (HVCI). Um dos recursos fornecidos pelo HVCI é o Credential Guard. O Credential Guard oferece os seguintes benefícios:

- **Segurança de hardware** NTLM, Kerberos e Credential Manager aproveitam os recursos de segurança da plataforma, incluindo Inicialização Segura e virtualização, para proteger credenciais.

- **A segurança baseada** em virtualização Windows credenciais derivadas NTLM e Kerberos e outros segredos executados em um ambiente protegido isolado do sistema operacional em execução.

- **Melhor proteção contra ameaças persistentes avançadas** Quando credenciais de domínio do Gerenciador de Credenciais, NTLM e credenciais derivadas kerberos são protegidas usando a segurança baseada em virtualização, as técnicas de ataque de roubo de credenciais e as ferramentas usadas em muitos ataques direcionados são bloqueadas. O malware executado no sistema operacional com privilégios administrativos não pode extrair segredos protegidos pela segurança baseada em virtualização.

## <a name="software-security"></a>Segurança de Software

Depois que o Microsoft Windows inicializar, Salas do Teams entrar automaticamente em uma conta de usuário Windows local chamada Skype. A Skype conta não tem senha. Para tornar a sessão Skype conta segura, as etapas a seguir são tomadas.

> [!IMPORTANT]
> Não altere a senha ou edite a conta de usuário local Skype usuário. Isso pode impedir Salas do Teams entrar automaticamente.

O Salas do Microsoft Teams aplicativo é executado usando o recurso Acesso Atribuído encontrado no Windows 10 1903 e posterior. O Access atribuído é um recurso no Windows 10 que limita os pontos de entrada do aplicativo expostos ao usuário. Isso é o que habilita o modo de quiosque de aplicativo único. Usando o Shell Launcher, Salas do Teams é configurado como um dispositivo de quiosque que executa um Windows de área de trabalho como a interface do usuário. O Salas do Microsoft Teams substitui o shell padrão (explorer.exe) que geralmente é executado quando um usuário faz o login. Em outras palavras, o shell tradicional do Explorer não é lançado. Isso reduz consideravelmente a superfície de Salas do Microsoft Teams de vulnerabilidade dentro Windows. Para obter mais informações, consulte [Configure kiosks and digital signs on Windows desktop editions](/windows/configuration/kiosk-methods).

Se você decidir executar uma verificação de segurança ou um parâmetro de referência do Centro para Segurança da Internet (CIS) no Salas do Teams, a verificação só poderá ser executado no contexto de uma conta de administrador local, pois a conta de usuário do Skype não dá suporte à execução de aplicativos que não sejam o aplicativo Salas do Teams. Muitos dos recursos de segurança aplicados ao contexto do usuário Skype não se aplicam a outros usuários locais e, como resultado, essas verificações de segurança não aparecerão no bloqueio de segurança total aplicado à conta Skype. Portanto, não é recomendável executar uma verificação local em Salas do Teams. No entanto, você pode executar testes de penetração externa, se assim desejar. Devido a isso, recomendamos que você execute testes de penetração externa em Salas do Teams dispositivos em vez de executar verificações locais.

Além disso, as políticas de bloqueio são aplicadas para limitar os recursos não administrativos de serem usados. Um filtro de teclado está habilitado para interceptar e bloquear combinações de teclado potencialmente inseguras que não são cobertas pelas políticas de Acesso Atribuído. Somente usuários com direitos administrativos locais ou de domínio têm permissão para entrar Windows gerenciar Salas do Teams. Essas e outras políticas aplicadas ao Windows em dispositivos Salas do Microsoft Teams são continuamente avaliadas e testadas durante o ciclo de vida do produto.

## <a name="account-security"></a>Segurança da Conta

Salas do Teams dispositivos incluem uma conta administrativa chamada "Admin" com uma senha padrão. Recomendamos que você altere a senha padrão assim que possível após concluir a instalação.

A conta de administrador não é necessária para a operação adequada de dispositivos Salas do Teams e pode ser renomeada ou até mesmo excluída. No entanto, antes de excluir a conta admin, certifique-se de configurar uma conta de administrador local alternativa configurada antes de remover a que acompanha Salas do Teams dispositivos. Para obter mais informações sobre como alterar uma senha para uma conta Windows local usando ferramentas de Windows ou PowerShell, consulte o seguinte:

- [Alterar ou redefinir sua Windows senha](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Você também pode importar contas de domínio para o grupo Windows Administrador local. Você pode fazer isso para contas do Azure AD usando o Intune. Para obter mais informações, consulte [CSP de política – RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!CAUTION]
> Se você excluir ou desabilitar a conta de administrador antes de conceder permissões de Administrador local a outra conta local ou de domínio, poderá perder a capacidade de administrar o dispositivo Salas do Teams local. Se isso acontecer, você precisará redefinir o dispositivo de volta para suas configurações originais e concluir o processo de instalação novamente.
>
> Não conceda permissões de administrador local à conta Skype usuário.

Windows O Designer de Configuração pode ser usado para criar Windows 10 de provisionamento. Além de alterar a senha de administrador local, você também pode fazer coisas como alterar o nome do computador e se registrar em Azure Active Directory. Para obter mais informações sobre como criar um Windows de provisionamento do Designer de Configuração, consulte [Provisionamento de pacotes para Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

Você precisa criar uma conta de recurso para cada dispositivo Salas do Teams para que ele possa entrar Teams. Não é possível usar a autenticação de dois fatores ou multifações com essa conta. Exigir um segundo fator impediria que a conta fosse capaz de entrar automaticamente no aplicativo Salas do Teams após uma reinicialização. No entanto, você pode habilitar a Autenticação Moderna para obter segurança adicional para essa conta. Além disso, as políticas de Acesso Condicional baseadas em local podem ser implantadas para a conta de recurso para impedir a entrada na conta de um local não aprovado. Para obter mais informações, consulte [Using the location condition in a Conditional Access policy](/azure/active-directory/conditional-access/location-condition)

Recomendamos que você crie a conta de recurso no Azure AD, se possível. Embora uma conta sincronizada possa funcionar com Salas do Teams implantações híbridas, essas contas sincronizadas geralmente têm dificuldade para entrar no Salas do Teams e podem ser difíceis de solucionar problemas. Se você optar por usar um serviço de federação de terceiros para autenticar as credenciais da conta de recurso, verifique se o IDP de terceiros responde com o `wsTrustResponse` atributo definido como `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Segurança de Rede

Geralmente, Salas do Teams tem os mesmos requisitos de rede que qualquer Microsoft Teams cliente. O acesso por firewalls e outros dispositivos de segurança é o mesmo Salas do Teams para qualquer outro cliente Microsoft Teams cliente. Específicas Salas do Teams, as categorias listadas como "necessárias" para Teams devem estar abertas no firewall. Salas do Teams também precisa de acesso ao Windows Update, Microsoft Store e Microsoft Intune (se você usar o Microsoft Intune para gerenciar seus dispositivos). Para ver a lista completa de IPs e URLs necessárias para Salas do Microsoft Teams, consulte:

- **Microsoft Teams** [Office 365 URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Atualizar** [Configurar O WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** [Pré-requisitos para Microsoft Store para Empresas e Educação](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [pontos de extremidade de rede para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Se você estiver usando o Salas do Microsoft Teams de serviços gerenciados do Salas do Microsoft Teams Premium, também precisa garantir que Salas do Teams possa acessar as SEGUINTES URLs:

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Salas do Teams é configurado para manter-se automaticamente remendado com as atualizações Windows mais recentes, incluindo as atualizações de segurança. Salas do Teams instala todas as atualizações pendentes todos os dias a partir das 2:00 usando uma política local pré-definida. Não é necessário usar ferramentas adicionais para implantar e aplicar Windows Atualizações. O uso de ferramentas adicionais para implantar e aplicar atualizações pode atrasar a instalação de Windows patches e, assim, levar a uma implantação menos segura. O Salas do Teams aplicativo é implantado usando o Microsoft Store. Se seus dispositivos são licenciados com Salas do Microsoft Teams Padrão, todas as novas versões do aplicativo são instaladas automaticamente durante o processo de correção noturna. Se seus dispositivos são licenciados com Salas do Microsoft Teams Premium e inscritos no Serviço Gerenciado da Microsoft, novas versões do aplicativo Salas do Teams são instaladas de acordo com seu plano de implantação definido.

Salas do Teams dispositivos funcionam com a maioria dos 802.1X ou outros protocolos de segurança baseados em rede. No entanto, não somos capazes de testar Salas do Teams todas as configurações de segurança de rede possíveis. Portanto, se surgirem problemas de desempenho que podem ser rastreados para problemas de desempenho de rede, talvez seja necessário desabilitar esses protocolos se eles estão configurados em sua organização.

Para um desempenho ideal de mídia em tempo real, recomendamos que você configure o tráfego de mídia Teams para ignorar servidores proxy e outros dispositivos de segurança de rede. A mídia em tempo real é muito sensível à latência e servidores proxy e dispositivos de segurança de rede podem degradar significativamente a qualidade de vídeo e áudio dos usuários. Além disso, como Teams mídia já está criptografada, não há benefício tangível de passar o tráfego por um servidor proxy. Para obter mais informações, consulte [Networking up (to the cloud) —](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) Um ponto de vista do arquiteto que discute as recomendações de rede para melhorar o desempenho da mídia com Microsoft Teams e Salas do Microsoft Teams.

> [!IMPORTANT]
> Salas do Teams não dá suporte a servidores proxy autenticados.

Salas do Teams dispositivos não precisam se conectar a uma LAN interna. Considere colocar o Salas do Teams em um segmento de rede seguro com acesso direto à Internet. Se sua LAN interna for comprometida, as oportunidades de vetor de ataque Salas do Teams serão reduzidas.

Recomendamos que você conecte seus dispositivos Salas do Teams a uma rede com fio. O uso de redes sem fio em Salas do Teams dispositivos não é recomendado ou certificado. Alguns recursos de conectividade, como Wi-Fi Sense, são desabilitados por padrão.

A Participação de Proximidade e outros Salas do Teams recursos dependem de Bluetooth. No entanto, Bluetooth implementação em dispositivos Salas do Teams não permite uma conexão de dispositivo externo a um Salas do Teams dispositivo. Bluetooth uso de tecnologia em Salas do Teams dispositivos atualmente está limitado a sinalizadores de publicidade e conexões proximales solicitados. O tipo pdu (unidade de dados `ADV_NONCONN_INT` de protocolo) é usado no sinalizador de publicidade. Esse tipo de PDU é para dispositivos não conectáveis que anunciam informações ao dispositivo de escuta. Não há Bluetooth de dispositivos como parte desses recursos. Detalhes adicionais sobre Bluetooth protocolos podem ser encontrados no site [Bluetooth SIG.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
