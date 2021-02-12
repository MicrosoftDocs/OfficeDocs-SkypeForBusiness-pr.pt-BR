---
title: Segurança de Salas do Microsoft Teams
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
description: Saiba como proteger seus dispositivos de Salas do Microsoft Teams.
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880863"
---
# <a name="microsoft-teams-rooms-security"></a>Segurança de Salas do Microsoft Teams

A Microsoft trabalha com nossos parceiros para fornecer uma solução segura e que não requer ações adicionais para proteger as Salas do Microsoft Teams. Este artigo aborda muitos dos recursos de segurança encontrados nas Salas do Teams.

> [!NOTE]
> As Salas do Microsoft Teams não devem ser tratadas como uma estação de trabalho típica do usuário final. Não apenas os casos de uso são muito diferentes, mas os perfis de segurança padrão também são muito diferentes.

Dados limitados do usuário final são armazenados em Salas do Teams. Os dados do usuário final podem ser armazenados nos arquivos de log apenas para solução de problemas e suporte. Em nenhum momento, um participante de uma reunião usando salas do Teams pode copiar arquivos para o disco rígido ou entrar como eles mesmos. Nenhum dado do usuário final é transferido ou acessado pelo dispositivo Salas do Microsoft Teams.

Embora os usuários finais não possam colocar arquivos em um disco rígido salas do Teams, o Microsoft Defender ainda está habilitado. O desempenho das Salas do Teams é testado com o Microsoft Defender. Desabilitar isso ou adicionar software de segurança do ponto de extremidade pode levar a resultados imprevisíveis e possível degradação do sistema.

## <a name="hardware-security"></a>Segurança de hardware

Em um ambiente de Salas do Teams, há um módulo de computação central que executa a edição do Windows 10 IoT Enterprise. Todos os módulos de computação certificados devem ter uma solução de montagem segura, um slot de bloqueio de segurança (por exemplo, Bloqueio de Kensington) e medidas de segurança de acesso à porta de I/O para impedir a conexão de dispositivos não autorizados. Você também pode desabilitar portas específicas por meio da configuração UEFI (Unified Extensible Firmware Interface).

Todos os módulos de computação certificados devem ser comunicados com a tecnologia compatível com Módulo de Plataforma Confiável (TPM) 2.0 habilitada por padrão. O TPM é usado para criptografar as informações de logon da conta de recurso Salas do Teams.

A inicialização segura é habilitada por padrão. A inicialização segura é um padrão de segurança desenvolvido por membros do setor de computadores para ajudar a garantir que um dispositivo seja inicializado usando apenas software confiável pelo Fabricante de Equipamento Original (OEM). Quando o computador é iniciado, o firmware verifica a assinatura de cada parte do software de inicialização, incluindo drivers de firmware UEFI (também conhecidos como ROMs de opção), aplicativos EFI e o sistema operacional. Se as assinaturas são válidas, o computador é inicializado e o firmware dá controle ao sistema operacional. Para obter mais informações, consulte [Inicialização segura.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

O acesso às configurações da UEFI só é possível anexando um teclado físico e um mouse. Isso impede que você possa acessar a UEFI por meio do console habilitado para toque de Salas do Teams, bem como qualquer outro vídeo habilitado para toque anexado às Salas do Teams.

A Proteção do DMA (Acesso Direto à Memória) do Kernel é uma configuração do Windows 10 habilitada nas Salas do Teams. Com esse recurso, o sistema operacional e o firmware do sistema protegem o sistema contra ataques DMA mal-intencionados e intencionais para todos os dispositivos compatíveis com DMA:

- Durante o processo de inicialização.

- Contra DMA mal-intencionado por dispositivos conectados a portas fáceis de acessar internas/externas compatíveis com DMA, como slots M.2 PCIe e Thunderbolt 3, durante o tempo de execução do sistema operacional.

As Salas do Teams também habilitam a integridade de código protegida por hipervisor (HVCI). Um dos recursos fornecidos pelo HVCI é o Credential Guard. O Credential Guard fornece os seguintes benefícios:

- **Segurança de hardware** O NTLM, Kerberos e o Gerenciador de Credenciais aproveitam os recursos de segurança da plataforma, incluindo Inicialização Segura e virtualização, para proteger as credenciais.

- **Segurança baseada em virtualização** As credenciais derivadas do Windows NTLM e Kerberos e outros segredos são executados em um ambiente protegido isolado do sistema operacional em execução.

- **Melhor proteção contra ameaças persistentes avançadas** Quando as credenciais de domínio derivadas do Gerenciador de Credenciais, NTLM e Kerberos são protegidas usando segurança baseada em virtualização, as técnicas e ferramentas de ataque de roubo de credenciais usadas em muitos ataques direcionados são bloqueadas. Malware em execução no sistema operacional com privilégios administrativos não pode extrair segredos protegidos por segurança baseada em virtualização.

## <a name="software-security"></a>Segurança do Software

Depois que o Microsoft Windows inicializar, as Salas do Teams entrarão automaticamente em uma conta de usuário local do Windows chamada Skype. A conta do Skype não tem senha. Para tornar a sessão de conta do Skype segura, as etapas a seguir são realizadas.

> [!IMPORTANT]
> Não altere a senha ou edite a conta de usuário local do Skype. Isso pode impedir que as Salas do Teams entre automaticamente.

O aplicativo Salas do Microsoft Teams é executado usando o recurso Acesso Atribuído encontrado no Windows 10 1903 e posterior. O Access atribuído é um recurso do Windows 10 que limita os pontos de entrada do aplicativo expostos ao usuário. Isso é o que habilita o modo quiosque de aplicativo único. Usando o Shell Launcher, as Salas do Teams estão configuradas como um dispositivo quiosque que executa um aplicativo da área de trabalho do Windows como interface do usuário. O aplicativo Salas do Microsoft Teams substitui o shell padrão (explorer.exe) que geralmente é executado quando um usuário faz o login. Em outras palavras, o shell tradicional do Explorer não é lançado. Isso reduz muito a superfície de vulnerabilidade das Salas do Microsoft Teams no Windows. Para obter mais informações, consulte [Configurar quiosques e placas digitais em edições da](https://docs.microsoft.com/windows/configuration/kiosk-methods)área de trabalho do Windows.

Se você decidir executar uma verificação de segurança ou um parâmetro de referência do Centro de Segurança da Internet (CIS) em Salas do Teams, a verificação só poderá ser executado no contexto de uma conta de administrador local, pois a conta de usuário do Skype não dá suporte à execução de aplicativos diferentes do aplicativo Salas do Teams. Muitos dos recursos de segurança aplicados ao contexto de usuário do Skype não se aplicam a outros usuários locais e, como resultado, essas verificações de segurança não aparecerão no bloqueio de segurança total aplicado à conta do Skype. Portanto, não é recomendável executar uma verificação local nas Salas do Teams. No entanto, você pode executar testes de danos externos, se assim desejar. Por isso, recomendamos que você execute testes de insuembação externa em dispositivos de Salas do Teams em vez de executar verificações locais.

Além disso, políticas de bloqueio são aplicadas para limitar o uso de recursos não administrativos. Um filtro de teclado está habilitado para interceptar e bloquear combinações de teclado potencialmente inseguras que não são cobertas pelas políticas do Access Atribuídas. Somente usuários com direitos administrativos locais ou de domínio têm permissão para entrar no Windows para gerenciar salas do Teams. Essas e outras políticas aplicadas ao Windows em dispositivos Microsoft Teams Rooms são constantemente avaliadas e testadas durante o ciclo de vida do produto.

## <a name="account-security"></a>Segurança da Conta

Os dispositivos salas do Teams incluem uma conta administrativa chamada "Administrador" com uma senha padrão. Recomendamos que você altere a senha padrão assim que possível após concluir a configuração.

A conta de administrador não é necessária para o funcionamento adequado de dispositivos de Salas do Teams e pode ser renomeada ou até mesmo excluída. No entanto, antes de excluir a conta de Administrador, certifique-se de configurar uma conta de administrador local alternativa configurada antes de remover a conta que acompanha os dispositivos salas do Teams. Para saber mais sobre como alterar uma senha de uma conta local do Windows usando ferramentas do Windows ou PowerShell, consulte o seguinte:

- [Alterar ou redefinir sua senha do Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Você também pode importar contas de domínio para o grupo administrador local do Windows. Você pode fazer isso para contas do Azure AD usando o Intune. Para obter mais informações, consulte [A política CSP – Grupos Restritos.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> Se você excluir ou desabilitar a conta de Administrador antes de conceder permissões de Administrador local a outra conta local ou de domínio, poderá perder a capacidade de administrar o dispositivo Salas do Teams. Se isso acontecer, você precisará redefinir o dispositivo para as configurações originais e concluir o processo de configuração novamente.
>
> Não conceda permissões de Administrador local à conta de usuário do Skype.

O Designer de Configuração do Windows pode ser usado para criar pacotes de provisionamento do Windows 10. Além de alterar a senha de administrador local, você também pode fazer coisas como alterar o nome do computador e se registrar no Azure Active Directory. Para obter mais informações sobre como criar um pacote de provisionamento do Windows Configuration Designer, consulte [Provisionamento de pacotes para Windows 10.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Você precisa criar uma conta de recurso para cada dispositivo de Salas do Teams para que ele possa entrar no Teams. Você não pode usar a autenticação de dois fatores ou multifafa com essa conta. Exigir um segundo fator impediria que a conta fosse capaz de entrar automaticamente no aplicativo Salas do Teams após uma reinicialização. No entanto, você pode habilitar a Autenticação Moderna para obter mais segurança para essa conta. Além disso, as políticas de Acesso Condicional baseadas em locais podem ser implantadas para a conta de recurso para impedir a entrada na conta de um local não aprovado. Para obter mais informações, [consulte Usando a condição de local em uma política de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

Recomendamos que você crie a conta de recurso no Azure AD, se possível. Embora uma conta sincronizada possa funcionar com salas do Teams em implantações híbridas, essas contas sincronizadas geralmente têm dificuldade para entrar em Salas do Teams e podem ser difíceis de solucionar problemas. Se você optar por usar um serviço de federação de terceiros para autenticar as credenciais da conta de recurso, certifique-se de que o IDP de terceiros responda com o `wsTrustResponse` atributo definido como `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Segurança de Rede

Em geral, as Salas do Teams têm os mesmos requisitos de rede que qualquer cliente do Microsoft Teams. O acesso por firewalls e outros dispositivos de segurança é o mesmo para Salas do Teams e para qualquer outro cliente do Microsoft Teams. Específicas das Salas do Teams, as categorias listadas como "necessárias" para o Teams devem estar abertas no firewall. As Salas do Teams também precisam de acesso ao Windows Update, à Microsoft Store e ao Microsoft Intune (se você usar o Microsoft Intune para gerenciar seus dispositivos). Para ver a lista completa de IPs e URLs necessárias para salas do Microsoft Teams, consulte:

- **URLs** e intervalos de endereços IP do Microsoft Teams [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Configuração do Windows Update** [WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Pré-requisitos** da Microsoft Store [para Microsoft Store para Empresas e Educação](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Network Enpoints para Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Se você estiver usando o componente de serviços gerenciados salas do Microsoft Teams do Microsoft Teams Rooms Premium, também precisará garantir que as Salas do Teams possam acessar as seguintes URLs:

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

As Salas do Teams estão configuradas para se manterem automaticamente corrigidas com as atualizações mais recentes do Windows, incluindo as atualizações de segurança. As Salas do Teams instalam todas as atualizações pendentes todos os dias a partir das 2h usando uma política local pré-definida. Não é necessário usar ferramentas adicionais para implantar e aplicar atualizações do Windows. Usar ferramentas adicionais para implantar e aplicar atualizações pode atrasar a instalação de patches do Windows e, portanto, levar a uma implantação menos segura. O aplicativo Salas do Teams é implantado usando a Microsoft Store. Se seus dispositivos são licenciados com o Microsoft Teams Rooms Standard, todas as novas versões do aplicativo são instaladas automaticamente durante o processo de patch noturno. Se seus dispositivos são licenciados com o Microsoft Teams Rooms Premium e inscritos no Serviço Gerenciado da Microsoft, novas versões do aplicativo Salas do Teams são instaladas de acordo com seu plano de implantação definido.

Os dispositivos salas do Teams funcionam com a maioria dos protocolos de segurança 802.1X ou outros protocolos de segurança baseados em rede. No entanto, não é possível testar salas do Teams em todas as possíveis configurações de segurança de rede. Portanto, se surgirem problemas de desempenho que podem ser rastreados para problemas de desempenho de rede, talvez seja necessário desabilitar esses protocolos se eles estão configurados em sua organização.

Para obter um desempenho ideal de mídia em tempo real, é recomendável configurar o tráfego de mídia do Teams para ignorar servidores proxy e outros dispositivos de segurança de rede. As mídias em tempo real são muito sensíveis à latência, e os servidores proxy e os dispositivos de segurança de rede podem prejudicar significativamente a qualidade de áudio e vídeo dos usuários. Além disso, como a mídia do Teams já está criptografada, não há benefício algum em passar o tráfego por um servidor proxy. Para obter mais informações, consulte [Networking up (para](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) a nuvem) — Um debate de arquitetura que discute recomendações de rede para melhorar o desempenho das mídias com o Microsoft Teams e as Salas do Microsoft Teams.

> [!IMPORTANT]
> As Salas do Teams não são suportadas por servidores proxy autenticados.

Os dispositivos salas do Teams não precisam se conectar a uma LAN interna. Considere colocar salas do Teams em um segmento de rede seguro com acesso direto à Internet. Se sua LAN interna for comprometida, as oportunidades vetoriais de ataque em salas do Teams serão reduzidas.

É recomendável conectar seus dispositivos de Salas do Teams a uma rede com fio. O uso de redes sem fio em dispositivos salas do Teams não é recomendado ou certificado. Alguns recursos de conectividade, como o Wi-Fi Sense, são desabilitados por padrão.

O Join de Proximidade e outros recursos de Salas do Teams dependem do Bluetooth. No entanto, a implementação do Bluetooth em dispositivos salas do Teams não permite uma conexão de dispositivo externo com um dispositivo salas do Teams. No momento, o uso de tecnologia Bluetooth em dispositivos salas do Teams está limitado a sinalizadores de anúncio e conexões de conexões de bluetooth. O `ADV_NONCONN_INT` tipo de unidade de dados de protocolo (PDU) é usado no sinalizador de publicidade. Esse tipo de PDU é para dispositivos não conectáveis que anunciam informações ao dispositivo atento. Não há emparelhamento de dispositivo Bluetooth como parte desses recursos. Detalhes adicionais sobre protocolos Bluetooth podem ser encontrados no [site Bluetooth BLUETOOTH.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
