---
title: Desabilitar o TLS 1.0/1.1 no Skype para Business Server 2015
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: Preparar e implementar desabilitando TLS 1.0 e 1.1 em seus ambientes.'
ms.openlocfilehash: e1e345da45c60637a8c6cf20061f8b0274a1474d
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347453"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Desabilitar o TLS 1.0/1.1 no Skype para Business Server 2015

A finalidade deste artigo é fornecer as diretrizes necessárias para você preparar e implementar desabilitando TLS 1.0 e 1.1 em seus ambientes. Esse processo exige amplo planejamento e preparação. Examine cuidadosamente todas as informações neste artigo à medida que você faz seu plano para desabilitar o TLS 1.0 e 1.1 para sua organização. Observe que há muitas dependências externas e condições de conectividade que podem ser afetadas por meio da desabilitação TLS 1.0/1.1, tão extenso de planejamento e teste é garantido.

## <a name="in-this-article"></a>Neste artigo

- [Plano de fundo e escopo](#background)
- [Pré-requisitos e processo](#prerequisites-and-process)
- [Cenários de implantação avançada](#advanced-deployment-scenarios)

## <a name="background"></a>Plano de fundo

Os principais fatores para fornecer TLS 1.0 e suporte de disable 1.1 para Skype para Business Server local são os requisitos de conselho de padrões de segurança do setor de cartões de pagamento (PCI) e os padrões de processamento de informações federais. Para obter mais informações para os requisitos de PCI podem ser encontradas [aqui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Não é possível para o Microsoft fornecem orientação sobre ou não a sua organização é obrigada aderir a essas ou outros requisitos. Você deve determinar se ele é necessário para desabilitar o TLS 1.0 e/ou 1.1 em seus ambientes.

Microsoft gerou um white paper sobre TLS disponíveis [aqui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), e também recomendamos o plano de fundo lendo disponíveis neste [blog do Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Escopo de suporte

*Escopo* refere-se aos limites de suporte. Para Skype para Business Server local, *no escopo* significa totalmente suportar e testamos a desabilitação de TLS 1.0 e 1.1 para as versões de produto listado. *Atualmente, sendo investigados* significa apenas que; estamos ativamente investigando trazendo esses produtos para o escopo para desativar o suporte a TLS. *Fora do escopo* significa dessas versões do produto não suportam desabilitando TLS 1.0 ou 1.1 e não funcionarão, com as exceções indicadas.

### <a name="fully-tested-and-supported-servers"></a>Servidores totalmente testadas e suportadas

- Skype para Business Server 2019
- Skype para Business Server 2015 CU6 HF2 6.0.9319.516 ([março 2018 atualizar](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) e superiores em: 
    - Windows Server 2012 (com 3140245 KB ou atualização que substitui), 2012 R2 ou 2016
- In-loco atualizados Skype para Business Server 2015, com CU6 HF2 e superiores em 
    - Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização que substitui) ou 2012 R2
- Conectividade do Exchange e Outlook Web App com RU19 do Exchange Server 2010 SP3 ou superior, orientação [aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
 
### <a name="fully-tested-and-supported-clients"></a>Clientes totalmente testados e suportados

- O cliente de Desktop do Lync 2013 (Skype for Business), MSI e C2R, incluindo Basic [15.0.5023.1000 e superiores](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype para negócios 2016 Desktop Client, MSI [16.0.4678.1000 e superiores](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluindo Basic
- Skype para negócios 2016, clique executar exigem as atualizações de [abril 2018](https://docs.microsoft.com/en-us/officeupdates/release-notes-office365-proplus) : 
    - Mensal e anual delimitadas direcionadas, 16\.0\.9126\.2152 e superiores
    - Anual delimitadas e canal adiada, 16\.0\.8431\.2242 e superiores
- Skype for Business no Mac 16.15 e superior
- Skype para empresas para iOS e Android 6.19 e superior
- Skype Web App 2015 CU6 HF2 e superior (fornecido com o servidor)

### <a name="currently-being-investigated"></a>Atualmente, sendo investigados

#### <a name="devices"></a>Dispositivos

- O sistema de sala do Lync (também conhecido como SRSv1)
- Sistemas de sala Skype v2 (também conhecido como SRSv2)
- Surface Hub
- 2015 baseados aparelho de filial persistente (SBA) ou o servidor de filial persistente (SBS)

#### <a name="other"></a>Outros

- Painel de controle de qualidade de chamada (nova instalação após TLS 1.0, 1.1 foram desabilitadas, veja abaixo) *
 
### <a name="out-of-scope"></a>Fora do escopo

Exceto onde observado, os produtos a seguir não estão no escopo para suporte a TLS 1.0/1.1 disable e não funcionarão em um ambiente onde TLS 1.0 e 1.1 foram desabilitadas.  O que isso significa: se você ainda utiliza clientes ou servidores fora do escopo, você deve atualizar ou removê-los a se você precisar desativar TLS 1.0/1.1 em qualquer lugar no seu Skype para Business Server implantação local.

- Lync Server 2013 *
- Windows Server 2008 e inferior
- Lync para Mac 2011
- Lync 2013 para dispositivos móveis - iOS, iPad, Android ou do Windows Phone
- Cliente do Lync "MX" Windows Store
- Todos os clientes do Lync 2010
- Lync Phone Edition - atualizada a orientação [aqui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- Aparelho de filial persistente (SBA) ou o servidor de filial persistente (SBS) com base em 2013

### <a name="exceptions"></a>Exceções

#### <a name="lync-server-2013"></a>* O Lync Server 2013

Lync Server 2013 assume uma dependência versão 1.0 do Windows Fabric.  Na fase de design do Lync Server 2013, Windows Fabric 1.0 foi escolhido para sua arquitetura distribuída nova e atraente fornecer replicação, alta disponibilidade e tolerância a falhas.  Ao longo do tempo, ambos os Skype para Business Server e Windows Fabric melhoraram muito essa arquitetura conjunta com significativo refaça o projeto em versões subsequentes.  Skype atual para o Business 2015 Server usa o Windows Fabric 3.0, por exemplo.

Infelizmente, o Windows Fabric 1.0 **não oferece suporte a TLS 1.2.  No entanto, atualizaremos Lync Server 2013 para trabalhar com o TLS 1.2**. Isso estará disponível na próxima atualização cumulativa para o Lync Server 2013.  Estamos fornecendo suporte a TLS 1.2 para permitir que os cenários de coexistência, migração, Federação e híbrida.

Se sua organização é obrigada para desabilitar o TLS 1.0 e 1.1 e Lync Server 2013 atualmente em uso, é recomendável começar o processo de planejamento, com a possibilidade talvez seja necessário atualização in-loco ou lado a lado migrar (novos pools, mover usuários) para Skype para Servidor de negócios 2015 ou superior.  Ou talvez você queira acelerar a migração para Skype para negócios Online.

#### <a name="call-quality-dashboard"></a>* O painel de controle de qualidade de chamada

Painel de qualidade de chamada local atualmente tem uma dependência em TLS 1.0 durante a nova instalação (primeira vez instalando em seus ambientes de local).  Estamos atualmente investigando esse problema e planeje liberar uma correção no futuro próximo.  Se você estiver planejando instalar CQD e também desabilitar TLS 1.0, recomendamos que você concluir a instalação de CQD primeiro e, em seguida, continue com a desativação de TLS 1.0.

#### <a name="third-party-devices"></a>Dispositivos de terceiros

Em dispositivos de terceiros, como telefones 3PIP, conferência de vídeo, Proxies reversos e balanceadores de carga, certifique-se validar o suporte de TLS 1.2, teste cuidadoso e contate o fornecedor, se necessário.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considerações sobre a federação desabilitando TLS 1.0/1.1 nos servidores de borda

Cuidadosamente, você deve planejar e considerar o impacto da desativação TLS 1.0/1.1 em seus servidores de borda.  Depois que o TLS 1.0 e 1.1 estiverem desativados, você pode descobrir que outras organizações estão deixará de ser capaz de estabelecer uma federação com sua organização.

Você pode optar por manter o TLS 1.0/1.1 estiver habilitada nos servidores de borda para manter a compatibilidade com versões anteriores com não-corrigidas (SfB 2015, Lync 2013) ou mais antigos sistemas externos de (2010).

Microsoft não pode fornecer conselhos ou recomendações no ou não a sua rede de borda (ou qualquer rede) cai sob padrão; PCI que deve ser determinado pela empresa individual.

Skype para Business Online é capaz de TLS 1.2 atualmente, portanto, nenhum impacto híbrida/federação com Online é esperado.

PIC (conectividade de IM pública) ao serviço de consumidor do Skype: não esperamos desabilitando TLS 1.0/1.1 para que possam afetar a [Conectividade do Skype](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways já estão TLS 1.2 capaz.

## <a name="prerequisites-and-process"></a>Pré-requisitos e processo

Exceto quando observado acima, depois que o TLS 1.0 e 1.1 são desabilitados fora do escopo de servidores, clientes e dispositivos mais funcionará corretamente, ou. Isso pode significar que você precisa fazer uma pausa e aguarde atualizada a orientação da Microsoft. Quando você estiver satisfeito que atender a todos os requisitos e ter um plano para intervalos de endereço, continue.

Em um alto nível, embora Skype para Business Server 2019 está pronta para o procedimento de instalação, Skype para Business Server 2015 exigirá que você instale CU6 HF2, aplicando atualizações de pré-requisito .NET e SQL, implantando chaves de registro de pré-requisito e finalmente um separado atualizações de ida da configuração do sistema operacional (isto é, desabilitando TLS 1.0 e 1.1 por meio da importação do arquivo de registro). É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo Skype para Business Server 2015 CU6 HF2, antes da desativação TLS 1.0 e 1.1 em qualquer servidor em seu ambiente. Cada Skype para Business server, incluindo a função de borda e SQL back-ends, requer as atualizações. Além disso, certifique-se de que todos os clientes suportados de (no escopo) foram atualizados com as versões mínimas necessárias. Não se esqueça de atualizar estações de trabalho de gerenciamento.

Queremos seguem a ordem usual de operações do "dentro para fora" para atualizar o Skype para servidores de negócios. Trate os pools de diretor, Pchat e Pools emparelhada da mesma maneira que faria normalmente. Ordem e métodos de atualização são abordados [aqui](topology.md) e [aqui](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processo de alto nível

1. Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.
2. Fazer backup e preservar uma cópia do registro exportado em cada servidor individual a ser atualizado. Não é possível compartilhar registros entre servidores; elas contêm teclas exclusivas baseada na máquina.
3. Atualize todos os Skype para servidores de negócios 2015 para CU6 HF2 ou superior. (Para Skype para Business Server 2019, nenhuma CU é necessária)
4. Instale todos os pré-requisitos para todos os servidores.
5. Implante chaves do registro de pré-requisito.
6. Certifique-se de que todos os clientes no escopo serão atualizados.
7. Desabilite o TLS 1.0 e 1.1 por meio da importação do registro.
8. Valide que as cargas de trabalho estão funcionando conforme o esperado.
    - Se forem encontrados problemas, solucionar e resolver, ou
    - Restaurar o registro da etapa 2 para reabilitar o TLS 1.0 e 1.1
9. Valide que apenas o TLS 1.2 está sendo usado.

### <a name="install-prerequisites-to-all-servers"></a>Instalar os pré-requisitos para todos os servidores

A atualização de dependência extensiva é necessária antes de começar a desativar o TLS 1.0 e 1.1 no nível do sistema operacional no seu Skype para implantações de negócios Server 2015. Estas são as versões mínimas que podem oferecer suporte a TLS 1.2. Implante todas as atualizações de pré-requisito em cada Skype para Business server no seu ambiente antes de começar desabilitando TLS 1.0 e 1.1.

- Skype para Business Server 2015 CU6 HF2 6.0.9319.516 ([atualização de março 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) ou superior
- [4.7 do .NET framework](https://www.microsoft.com/en-us/download/details.aspx?id=55167) ou superior com SchUseStrongCrypto habilitada no registro (fornecido abaixo)
- SQL deve ser atualizado em todos os Skype para servidores de negócios 2015 e back-ends. Atualize back-ends Enterprise Edition Pool SQL em primeiro lugar, em seguida, seus respectivos FEs. 
    - SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)) ou superior / SQL Server 2012 SP2 + CU16 ou superior / RTM do SQL Server 2014 + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) ou superior / 2014 do SQL Server SP2
    - SQL Server Native Client para SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - Microsoft ODBC Driver 11 para o SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) ou superior
    - Objetos de gerenciamento compartilhado para o SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
    - SQLSysClrTypes para o SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
 
### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Etapas básicas para instalar os pré-requisitos, na ordem recomendada de operações

1. Instale o Skype para Business Server CU6HF2 (6.0.9319.516) atualizar a todos os servidores. 
    1. Instale a atualização para os componentes usando o atualizador.
    2. Atualize bancos de dados de acordo com os procedimentos documentados. Instruções são documentadas em [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).
    3. Valide a funcionalidade do produto na implantação antes de continuar com qualquer outra alteração.
2. Baixe o .NET 4.7 instalador Offline. 
    1. Referência:[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. Certifique-se de que o Skype para serviços de Business Server 2015 são interrompidos no servidor Front-End.
    3. Referência:[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): Stop-CsWindowsServices
    5. Ex (Enterprise Edition): Invoke-CsComputerFailover
    6. Execute o pacote do instalador.
    7. Reinicialize o servidor.
3. Atualize o SQL Express 2014 em todos os servidores. 
    1. Referência:[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Baixe o SQL 2014 SP2 
        - Referência:[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. Copie a mídia de instalação para uma pasta no servidor (ex.: C:\01_2014SqlSp2)
    4. Certifique-se de Skype para os serviços são interrompidos em servidor Front-End do Business Server 2015 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    5. Abra um Prompt de comando do administrador e atualizar todos os componentes instalados e instâncias 
        - Exemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = Patch /AllInstances
4. Atualize o SQL Native Client. 
    1. Referência: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Baixar a partir[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. Certifique-se Skype para os serviços são interrompidos em servidor Front-End do Business Server 2015. 
        - Ex (Standard Edition): Stop-CsWindowsServices
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    4. Pare as instâncias do SQL instaladas sejam executados 
        - Ex.: Get-Service 'MSSQL$ RTCLOCAL' | STOP-serviço
        - Ex.: Get-Service 'MSSQL$ LYNCLOCAL' | STOP-serviço
        - Ex (Standard Edition apenas): Get-Service 'MSSQL$ RTC' | STOP-serviço
    5. Atualize a atualização.
5. Atualize o Driver ODBC 11 para o SQL Server. 
    1. Referência: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Baixar a partir[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. Certifique-se de que o Skype para serviços de Business Server 2015 são interrompidos no servidor Front-End 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    4. Atualize a atualização.
6. Implante chaves do registro de pré-requisito.

### <a name="pre-requisite-registry-keys"></a>Chaves do registro de pré-requisito

Copiar/colar o seguinte teste no bloco de notas e renomeie TLSPreReq.reg ou um nome de sua escolha, importar:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

Para o SQL back ends para Pools do Enterprise Edition, os pré-requisitos e TLS desabilitar deve ser tratado como faria com quaisquer atualizações SQL ou o sistema operacional; Consulte o artigo:[https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Enquanto o aplicativo de pré-requisito e o TLS desabilitando etapas podem ser combinadas, é altamente recomendável que todos os pré-requisitos a ser aplicado antes de prosseguir com a desativação de TLS 1.0 e 1.1 no nível do sistema operacional. A abordagem de prática recomendada seria preparar o ambiente implantando todos os pré-requisitos, validando que todas as cargas de trabalho funcionam corretamente e conforme o esperado, e então prosseguir com TLS 1.0/1.1 desabilitar mais tarde.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Desabilitar o TLS 1.0 e 1.1 por meio da importação de registro

Antes que você prosseguir com as próximas etapas, *Certifique-se de ter concluído a todos os pré-requisitos e atualizado Skype para servidores de negócios*.

Copie o seguinte texto em um arquivo do bloco de notas e renomeie- **TLSDisable.reg**:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

Importe o arquivo. reg em cada servidor que você deseja desativar o TLS 1.0 e 1.1. Reinicialize o servidor. Uma vez que os serviços tenham online novamente, mova para o próximo servidor. A abordagem para Pools do Enterprise Edition é a mesma que você percorreria para qualquer atualização de sistema operacional.

Você deve ter percebido que fazemos mais do que apenas desabilitando TLS 1.0 e 1.1 aqui. Podemos suporte para conjunto de codificação reordenar (conforme mostrado acima) e a desativação de alguns codificações fracas mais antigas. Esta é a primeira vez em que podemos oficialmente suportada essas alterações SCHANNEL e a API de criptografia no Skype para Business Server, e é importante observar que essas alterações são as únicas, podemos suportar e testado neste momento. Ainda considerarem configurações adicionais no futuro, mas no momento, não modifique o arquivo de importação do registro na sua implementação.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Validar que cargas de trabalho estão funcionando conforme o esperado

Depois que o TLS 1.0 e 1.1 foram desabilitadas em seu ambiente, certifique-se de que todas as suas cargas de trabalho principais estão funcionando conforme o esperado, como mensagens Instantâneas e presença, P2P chama, Enterprise Voice, etc.

**Validar apenas TLS 1.2 está sendo usado.**

Ter sua equipe de segurança para realizar uma auditoria nova do Skype para tráfego de negócios para garantir que a antiguidade protocolos TLS 1.0 e 1.1 não estão mais em uso.

Como alternativa, você pode usar o Internet Explorer para testar conexões TLS aos serviços web do Skype Business Server 2015 depois 1.0 TLS e TLS 1.1 foram desabilitados.

1. Inicie o Internet Explorer.
2. Selecione **Ferramentas** > **Opções da Internet**.
3. Selecione a guia **Avançado** .
4. Em **configurações**, navegue até o fim.
5. Verificar se o TLS 1.0, 1.1 TLS e TLS 1.2 estiver habilitado.
6. Procure a URL interna do serviço Web do seu pool SfB 2015 (deve se conectar com êxito).
7. Volte para o Internet Explorer e desabilite a opção para **Usar TLS 1.2** apenas.
8. Procure a URL interna do serviço Web do seu pool SfB 2015 novamente (deve Falha na conexão).

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Cenários de implantação avançada

Pois alguns pré-requisitos de dependência são necessárias para dar suporte a TLS 1.2 no Skype para negócios Ser 2015, instalando da mídia RTM falhará em qualquer sistema onde TLS 1.0 e 1.1 foram desabilitadas.

**Implantando os novos servidores do Standard Edition ou Enterprise Edition Pools depois que o TLS 1.0 e 1.1 foram desabilitadas em seu ambiente.**

**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Observe que estiver atualizando SmartSetup para acomodar os binários atualizados do SQL em um futuro CU e atualizará este artigo no futuro.

**Opção 2:** Pré-instalar instâncias SQL locais (RTCLOCAL e LYNCLOCAL)

1. Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64.exe) para uma pasta local na FE. Digamos que o caminho da pasta < SQL_FOLDER_PATH >.
2. Inicialize o PowerShell ou o Prompt de comando e navegue até < SQL_FOLDER_PATH >.
3. Crie a instância SQL RTCLOCAL executando o comando a seguir. Aguarde até que o SQLEXPR_x64.exe é concluída antes de prosseguir:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Install/recursos = SQLEngine, ferramentas /INSTANCENAME = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT\NETWORKSERVICE" /SQLSYSADMINACCOUNTS = "Builtin\ Os administradores"/BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT"Automática"="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automáti
1. Crie a instância SQL LYNCLOCAL executando o comando a seguir. Aguarde até que o SQLEXPR_x64.exe é concluída antes de prosseguir para a próxima etapa:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Install/recursos = SQLEngine, ferramentas /INSTANCENAME = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT\NETWORKSERVICE" /SQLSYSADMINACCOUNTS = "Builtin\ Os administradores"/BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT"Automática"="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automático
1. Execute Skype para instalação Business Server 2015 RTM.
2. Siga as etapas restantes da seção pré-requisitos acima.

**Opção 3:** Você pode substituir também manualmente binários em um diretório de mídia de instalação local da seguinte maneira:

1. [Instalar os pré-requisitos para Skype para Business Server](../../deploy/install/install-prerequisites.md)  
2. 2. Instale o .NET 4.7: 
    - **Observação:** Podemos introduzidos suporte para .NET 4.7 no Skype para Business Server 2015 CU5 + (6.0.9319.281). Portanto, nas etapas posteriores abaixo atualizaremos componentes principais antes da instalação principal.
    - Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.
    - Referência: [Software que deve ser instalado antes de um Skype para implantação Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copie os arquivos/pastas de ISO: 
    - Com o Skype para Business Server 2015 ISO anexado, abra o diretório raiz da unidade do qual ele está conectado como (ex.: D:\) no Gerenciador de arquivos.
    - Copie todos os arquivos e pastas em uma pasta em um disco local (ex.: C:\SkypeForBusiness2015ISO).
    - **Observação:** Antes de instalar os componentes, alguns arquivos precisarão ser atualizadas para oferecer suporte a TLS 1.2.
4. Substitua os pacotes MSI/EXE: 
    - Substitua os pacotes MSI e EXE existentes na pasta/amd64//Setup da mídia de instalação na máquina local.
    - SQL Express Edition SP2 de 2014:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Renomeie para SQLEXPR_x64 na máquina local e substituir o arquivo existente na instalação/amd64/pasta da mídia de instalação.
    - O SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Observação:** Renomear isso se necessário, para SQLNCLI e, em seguida, substituir o arquivo existente que existe na instalação/amd64/pasta da mídia de instalação.
    - Objetos de gerenciamento de SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Observação:** Feature pack terá muitos itens que podem ser baixados. Selecione esta opção para baixar SharedManagementObjects.msi somente.
        - **Observação:** Substituir o arquivo existente que existe na instalação/amd64/pasta da mídia de instalação.
    - Tipos CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Observação:** Feature pack terá muitos itens que podem ser baixados. Selecione essa opção para baixar CQLSysClrTypes.msi apenas
        - **Observação**: substituir o arquivo existente que existe na instalação/amd64/pasta da mídia de instalação.
5. Instale os componentes principais: 
    - Executar Setup.exe a partir do programa de instalação/amd64/pasta da mídia de instalação. Siga as instruções para instalar os componentes principais
    - Feche componentes principais.
6. Atualize componentes principais: 
    - Baixe o Skype para o instalador da atualização de negócios.
    - Execute o instalador para atualizar os componentes principais e instalar os contadores de desempenho.
    - **Observação:** Desde o lançamento do CU6HF2, o recurso de atualização automática atualmente apenas instalará até CU6. Portanto, o atualizador deve ser executado separadamente para atualizar os componentes principais para 6.0.9319.516.
    - Referência:https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Instale as ferramentas administrativas (opcionais): 
    - Isso instalará o Microsoft SQL Server 2012 Native Client, objetos de gerenciamento 2014 (x64) do SQL Server e Microsoft System CLR Types for SQL Server 2014 (x64) usando os arquivos atualizados. Além disso, o Skype para painel de controle e o construtor de topologias do Business Server 2015 estarão disponível na máquina local.
8. Repositório de configuração Local Install (etapa 1): 
     - Abrir o Assistente de implantação, clique em instalar ou atualizar Skype para Business Server System e clique em **Executar** na etapa 1: instalar repositório de configuração Local.
     - Clique em **Avançar** na caixa de diálogo **Instalar repositório de configuração Local** .
     ![Caixa de diálogo instalar repositório de configuração Local](../../media/local-configuration-store.png)
     - Revise os resultados e certifique-se de que o Status da tarefa é concluído. Revise o arquivo de log resultante clicando em **Exibir Log**.
     ![Status da tarefa mostra como concluído](../../media/local-configuration-task-completed.png)
     - Clique em **Concluir**.
9. Configurar ou remover Skype para componentes de servidor de negócios (etapa 2):
    - Abrir o Assistente de implantação, clique em **instalar ou atualização Skype para Business Server System**e clique em **Executar** na etapa 2: configurar ou remover Skype para componentes de servidor de negócios
    - Clique em **Avançar** na definir backup Skype para caixa de diálogo de componentes de servidor de negócios.
    ![a definir backup Skype para a janela de componentes de servidor de negócios](../../media/set-up-skype-for-business-server-components-window.png)
    - Examine o log usando o modo de exibição de Log e validar a instalação efetuada sem problemas. 
    - Clique em **Concluir**.
10. Prossiga com adicionais de instalação e configuração conforme necessário (você pode retomar procedimentos de instalação normal nesse momento).
