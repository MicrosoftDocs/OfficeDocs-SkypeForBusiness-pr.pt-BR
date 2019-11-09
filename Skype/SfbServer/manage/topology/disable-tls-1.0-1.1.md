---
title: Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: preparar e implementar a desabilitação do TLS 1,0 e do 1,1 em seus ambientes.'
ms.openlocfilehash: ce158aeaa84e00367b265404fe3d3407606f4759
ms.sourcegitcommit: f3b698379eb663202ce127eeaf6c07328c166556
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2019
ms.locfileid: "38077434"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015

O objetivo deste artigo é fornecer as diretrizes necessárias para se preparar e implementar a desabilitação do TLS 1,0 e do 1,1 em seus ambientes. Esse processo requer planejamento e preparação extensivos. Revise cuidadosamente todas as informações deste artigo enquanto faz seu plano para desativar o TLS 1,0 e o 1,1 para sua organização. Observe que há muitas dependências externas e condições de conectividade que podem ser impactadas ao desabilitar o TLS 1.0/1.1, portanto, o planejamento e o teste extensivos são garantidos.

## <a name="in-this-article"></a>Neste artigo

- [Plano de fundo e escopo](#background)
- [Pré-requisitos e processo](#prerequisites-and-process)
- [Cenários de implantação avançados](#advanced-deployment-scenarios)

## <a name="background"></a>Plano de fundo

Os principais drivers para fornecer o TLS 1,0 e o 1,1 Disable support para o Skype for Business Server no local são o Conselho de padrões de segurança da indústria de cartão de pagamento (PCI) e os padrões federais de processamento de informações. Mais informações para requisitos de PCI podem ser encontradas [aqui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  A Microsoft não pode fornecer orientação sobre a necessidade ou não de sua organização de aderir a esses ou outros requisitos. Você deve determinar se é necessário desativar o TLS 1,0 e/ou 1,1 em seus ambientes.

A Microsoft produziu um White paper sobre o TLS disponível [aqui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), e também recomendamos a leitura em segundo plano disponível neste [blog do Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Escopo de suporte

*Escopo* refere-se aos limites de suporte. *Totalmente testado e com suporte* significa que damos suporte e testamos a desativação do TLS 1,0 e do 1,1 para as versões de produto listadas. *Sendo investigado no momento* significa exatamente isso; Estamos investigando ativamente os produtos em escopo para desabilitar o suporte para TLS. *Fora do escopo* significa que essas versões do produto não são compatíveis com a desabilitação do TLS 1,0 ou do 1,1 e não funcionarão com exceções observadas.

### <a name="fully-tested-and-supported-servers"></a>Servidores totalmente testados e com suporte

- Skype for Business Server 2019 CU1 17.0.2046.123 (2019 de junho) ou superior
- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior no Windows Server 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização substituída), 2012 R2 ou 2016.
- Atualizado no local o Skype for Business Server 2015, com o CU9 6.0.9319.548 (2019 de maio) ou superior no Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização substituta) ou 2012 R2.
- Exchange conectividade e Outlook Web App com Exchange Server 2010 SP3 RU19 ou superior, orientação [aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Aplicativo de ramificação sobreviventes (SBA) com o Skype for Business Server 2015 CU6 HF2 ou superior (confirme com o seu fornecedor se eles empacotaram as atualizações do appropiate e se foram disponibilizados para o seu aparelho)
- Servidor de ramificação sobreviventes (SBS) com o Skype for Business Server 2015 CU6 HF2 ou superior
- **Somente função de borda**do Lync Server 2013, isso ocorre porque a função Edge não tem dependência no Windows Fabric 1,0.

### <a name="fully-tested-and-supported-clients"></a>Clientes totalmente testados e com suporte

- Lync 2013 (Skype for Business) Desktop Client, MSI e C2R, incluindo o [15.0.5023.1000 básico ou superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Cliente de área de trabalho Skype for Business 2016, MSI [16.0.4678.1000 ou superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluindo básico
- Skype for Business 2016 clique em para executar exige as atualizações de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Mensalmente e semidirecionado, 16\.0\.9126\.2152 ou superior
    - Canal semestral e semiadiado, 16\.0\.8431\.2242 ou superior
- Skype for Business no Mac 16,15 ou superior
- Skype for Business para iOS e Android 6,19 ou superior
- Salas do Microsoft Teams (anteriormente conhecido como Skype Room System v2 SRS v2) 4.0.64.0 (dezembro de 2018) ou superior
- Atualização do Surface Hub para Team Edition com base no KB4499162 (maio de 2019, versão do sistema operacional 15063,1835) ou superior
- Skype Web App 2015 CU6 HF2 ou superior (fornecido com o servidor)

### <a name="currently-being-investigated"></a>Sendo investigado no momento

- Painel de qualidade de chamada (nova instalação após o TLS 1,0, o 1,1 foi desabilitado, veja abaixo) *
 
### <a name="out-of-scope"></a>Fora do escopo

Exceto onde observado, os seguintes produtos não estão no escopo para TLS 1.0/1.1 desabilitar o suporte e não funcionarão em um ambiente em que o TLS 1,0 e o 1,1 foram desabilitados. O que isso significa: se você ainda usar servidores ou clientes fora do escopo, será necessário atualizar ou removê-los se precisar desabilitar o TLS 1.0/1.1 em qualquer lugar na sua implantação local do Skype for Business Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 ou inferior
- Lync para Mac 2011
- Lync 2013 para celular-iOS, iPad, Android ou Windows Phone
- Cliente da Windows Store "MX" do Lync
- Sistema de sala do Lync (conhecido como SRSv1). O LRS atingiu o fim do suporte em 9 de outubro de 2018 e não será atualizado para dar suporte a TLS 1,2.
- Todos os clientes do Lync 2010
- Lync Phone Edition – orientação atualizada [aqui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013 (SBA) ou servidor de ramificação sobreviver (SBS) com base em
- Cloud Connector Edition (CCE)
- Skype for Business para Windows Phone

### <a name="exceptions"></a>Exceções

#### <a name="lync-server-2013"></a>Lync Server 2013

O Lync Server 2013 assume uma dependência na versão 1,0 do Windows Fabric.  Na fase de design do Lync Server 2013, o Windows Fabric 1,0 foi escolhido para sua arquitetura distribuída atraente e nova para fornecer replicação, alta disponibilidade e tolerância a falhas.  Ao longo do tempo, tanto o Skype for Business Server quanto o Windows Fabric melhoraram bastante a arquitetura conjunta, com o redesign significativo nas versões subsequentes.  O servidor atual do Skype for Business 2015 usa o Windows Fabric 3,0, por exemplo.

Infelizmente, o Windows Fabric 1,0 não **é compatível com TLS 1,2.  No entanto, atualizaremos o Lync Server 2013 para funcionar com o TLS 1,2**. Isso estará disponível na próxima atualização cumulativa do Lync Server 2013.  Estamos fornecendo suporte a TLS 1,2 para habilitar a coexistência, migração, Federação e cenários híbridos.

Se a sua organização for necessária para desativar o TLS 1,0 e o 1,1, e você estiver usando o Lync Server 2013, recomendamos que você comece seu processo de planejamento, com a possibilidade de poder ter a atualização in-loco ou migração lado a lado (novos grupos, mover usuários) para o Skype para Business Server 2015 ou superior.  Ou talvez você queira acelerar a migração para o Skype for Business online.

#### <a name="call-quality-dashboard"></a>Painel de Qualidade da Chamada

No momento, o painel de qualidade de chamada no local tem uma dependência no TLS 1,0 durante a nova instalação (primeira instalação nos seus ambientes locais).  No momento, estamos investigando esse problema e planejamos liberar uma correção em breve.  Se você estiver planejando instalar o CQD e também desabilitar o TLS 1,0, recomendamos que conclua a instalação do CQD primeiro e, em seguida, continue com o TLS 1,0 desativando.

#### <a name="third-party-devices"></a>Dispositivos terceirizados

Em dispositivos de terceiros, como telefones 3PIP, videoconferência, proxies inversos e balanceadores de carga, certifique-se de validar a capacidade de suporte do TLS 1,2, teste cuidadosamente e entre em contato com o fornecedor, se necessário.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considerações de Federação ao desabilitar o TLS 1.0/1.1 em servidores de borda

Você deve planejar cuidadosamente e considerar o impacto de desabilitar o TLS 1.0/1.1 em seus servidores Edge.  Quando o TLS 1,0 e o 1,1 estiverem desativados, você pode descobrir que outras organizações não podem mais se federar à sua organização.

Você pode optar por manter o TLS 1.0/1.1 habilitado em seus servidores de borda para manter a compatibilidade com versões anteriores de sistemas externos não corrigidos (SfB 2015, Lync 2013) ou mais antigos (2010).

A Microsoft não pode fornecer conselhos nem recomendações sobre se a rede de borda (ou qualquer rede) cai ou não no padrão PCI; Isso deve ser determinado pela empresa individual.

O Skype for Business Online é capaz de usar o TLS 1,2 hoje, portanto, não é esperado nenhum impacto no híbrido/Federação online.

PIC (conectividade de IM pública) para o serviço de consumidor da Skype: não esperamos desabilitar o TLS 1.0/1.1 para afetar a [conectividade do Skype](../../deploy/deploy-skype-connectivity.md); Os gateways PIC da Microsoft já são compatíveis com o TLS 1,2.

## <a name="prerequisites-and-process"></a>Pré-requisitos e processo

Exceto onde observado acima, depois que o TLS 1,0 e o 1,1 estiverem desativados, os clientes e dispositivos funcionarão mais corretamente ou de modo algum. Isso pode significar que você precisa pausar e esperar por diretrizes atualizadas da Microsoft. Quando tiver certeza de que atende a todos os requisitos e tiver um plano para atender às lacunas, continue.

Em um nível alto, embora o Skype for Business Server 2019 esteja pronto para o procedimento na instalação, o Skype for Business Server 2015 exigirá que você instale o CU9, aplicando atualizações pré-requisitos para .NET e SQL, implantando as chaves de registro de pré-requisito e, por fim, um o arredondamento de atualizações de configuração do sistema operacional (ou seja, desabilitar o TLS 1,0 e 1,1 via importação de arquivo do registro). É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo o Skype for Business Server 2015 CU6 HF2, antes de desabilitar o TLS 1,0 e o 1,1 em qualquer servidor do seu ambiente. Cada servidor Skype for Business, incluindo função Edge e back-ends SQL, requer as atualizações. Além disso, certifique-se de que todos os clientes com suporte (em escopo) foram atualizados para as versões mínimas necessárias. Não se esqueça de atualizar as estações de trabalho de gerenciamento também.

Queremos acompanhar a ordem usual de operações de "Inside Out" para atualizar os servidores do Skype for Business. Trate pools de directors, chats persistentes e pools emparelhados da mesma forma que normalmente faria. O pedido e os métodos de atualização são abordados [aqui](topology.md) e [aqui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processo de alto nível

1. Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.
2. Faça backup e preserve uma cópia do registro exportado em todos os servidores individuais a serem atualizados. Não é possível compartilhar registros entre servidores; Elas contêm chaves exclusivas baseadas em máquina.
3. Atualize todos os servidores do Skype for Business 2015 para o CU9 ou superior. Para o Skype for Business Server 2019, atualize para o CU1 ou superior.
4. Instale todos os pré-requisitos em todos os servidores.
5. Implantar as chaves de registro de pré-requisito.
6. Certifique-se de que todos os clientes em escopo sejam atualizados.
7. Desabilite o TLS 1,0 e o 1,1 via importação do registro.
8. Valide se as cargas de trabalho estão funcionando conforme esperado.
    - Se forem encontrados problemas, solucionar e resolver ou
    - Restaurar o registro da etapa 2 para habilitar novamente o TLS 1,0 e o 1,1
9. Valide se apenas o TLS 1,2 está sendo usado.

### <a name="install-prerequisites-to-all-servers"></a>Instalar pré-requisitos em todos os servidores

Uma atualização de dependência extensa é necessária antes de começar a desabilitar o TLS 1,0 e o 1,1 no nível do sistema operacional no Skype for Business Server 2015 implantações. Veja a seguir as versões mínimas que podem dar suporte ao TLS 1,2. Implante todas as atualizações de pré-requisito em cada servidor do Skype for Business em seu ambiente antes de começar a desabilitar o TLS 1,0 e o 1,1.

- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) ou superior com o SchUseStrongCrypto habilitado no registro (fornecido abaixo)
- O SQL deve ser atualizado em todos os servidores do Skype for Business 2015 e nos back-ends. Atualize o pool de SQL do pool do SQL back ends primeiro e depois o respectivo FEs. 
    - SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)) ou superior/sql Server 2012 SP2 + CU16 ou superior/sql Server 2014 RTM + CU12 ([link](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)) ou superior/SQL Server 2014 SP2
     - SQL Server Native Client para SQL Server 2012 ([link](https://www.microsoft.com/download/details.aspx?id=50402))
     - Microsoft ODBC Driver 11 para SQL Server ([link](https://www.microsoft.com/download/details.aspx?id=36434)) ou superior
     - Objetos de gerenciamento compartilhado para SQL Server 2014 SP2 ([link](https://www.microsoft.com/download/details.aspx?id=42295))
     - SQLSysClrTypes para SQL Server 2014 SP2 ([link](https://www.microsoft.com/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Etapas básicas para instalar pré-requisitos, em ordem de operações recomendada

1. Instale a atualização do Skype for Business Server CU9 em todos os servidores. 
    1. Instale a atualização dos componentes usando o atualizador.
    2. Atualize bancos de dados de acordo com os procedimentos documentados. Para o Skype for Business Server 2015, consulte KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Valide a funcionalidade do produto na implantação antes de prosseguir com outras alterações.
2. Baixe o instalador offline do .NET 4,7. 
    1. Referencie[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.
    3. Referencie[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (edição padrão):```Stop-CsWindowsService```
    5. Ex (edição Enterprise):```Invoke-CsComputerFailover```
    6. Execute o pacote de instalação.
    7. Reinicie o servidor.
3. Atualize o SQL Express 2014 em todos os servidores. 
    1. Referencie[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Baixar o SQL 2014 SP2 
        - Referencie[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copiar a mídia de instalação para uma pasta no servidor (por exemplo: C:\ 01_2014SqlSp2)
    4. Garantir que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end 
        - Ex (edição padrão):```Stop-CsWindowsService```
        - Ex (edição Enterprise):```Invoke-CsComputerFailover```
    5. Abrir um prompt de comando de administrador e atualizar todos os componentes e instâncias instalados 
        - Exemplo: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. Atualize o cliente nativo do SQL. 
    1. Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Baixar de[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Assegure-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end. 
        - Ex (edição padrão):```Stop-CsWindowsServices```
        - Ex (edição Enterprise):```Invoke-CsComputerFailover```
    4. Parar a execução de instâncias do SQL instaladas 
        - Estendi```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Estendi```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Exemplo (somente a edição padrão):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Atualize a atualização.
5. Atualize o ODBC Driver 11 para SQL Server para incluir o suporte para TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Baixe o [ODBC Driver 11 para SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.
        - Exemplo (edição padrão):```Stop-CsWindowsService```
        - Exemplo (Enterprise Edition):```Invoke-CsComputerFailover```
    3. Atualize a atualização.
6. Implantar as chaves de registro de pré-requisito.

### <a name="pre-requisite-registry-keys"></a>Chaves do registro de pré-requisito

Copie/cole o teste a seguir no bloco de notas e renomeie TLSPreReq. reg ou um nome de sua escolha e, em seguida, importe:

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

Para os back-ends do SQL para os pools do Enterprise Edition, os pré-requisitos e a desabilitação de TLS devem ser tratados como qualquer atualização do sistema operacional ou SQL. consulte:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Embora o aplicativo de pré-requisito e as etapas de desabilitação de TLS possam ser combinados, recomendamos enfaticamente que todos os pré-requisitos sejam aplicados antes de prosseguir com a desativação do TLS 1,0 e do 1,1 no nível do sistema operacional. A abordagem de práticas recomendadas seria preparar o ambiente implantando todos os pré-requisitos, Validando se todas as cargas de trabalho funcionam corretamente e conforme o esperado e, em seguida, prosseguindo com o TLS 1.0/1.1 desabilitado em um momento posterior.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Desabilitar o TLS 1,0 e o 1,1 via importação do registro

Antes de prosseguir com as próximas etapas, *Verifique se você concluiu todos os pré-requisitos e os servidores do Skype for Business atualizados*.

Copie o seguinte texto em um arquivo do bloco de notas e renomeie-o **TLSDisable. reg**:

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

Importe o arquivo. reg em cada servidor que você deseja desativar o TLS 1,0 e o 1,1. Reinicie o servidor. Depois que os serviços voltam a ficar online, mover para o próximo servidor. A abordagem dos pools da edição Enterprise é a mesma que faria para qualquer atualização do sistema operacional.

Você pode ter notado que estamos fazendo mais do que simplesmente desabilitar o TLS 1,0 e 1,1 aqui. Estamos oferecendo o reordenamento do pacote de codificação (conforme mostrado acima) e a desativação de algumas cifras fracas mais antigas. Esta é a primeira vez que damos suporte a essas alterações para a API SCHANNEL e crypto no Skype for Business Server, e é importante observar que essas alterações são as únicas para as quais damos suporte e que testamos no momento. Podemos considerar configurações adicionais no futuro, mas por enquanto, não modifique o arquivo de importação do registro na sua implementação.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Validar que as cargas de trabalho estão funcionando como esperado

Quando o TLS 1,0 e o 1,1 estiverem desabilitados em seu ambiente, certifique-se de que todas as cargas de trabalho principais estejam funcionando como esperado, como mensagens instantâneas & presença, chamadas ponto a ponto, Enterprise Voice etc.

**Validar somente o TLS 1,2 está sendo usado**

Faça com que sua equipe de segurança realize uma nova auditoria do tráfego do Skype for Business para garantir que os protocolos mais antigos TLS 1,0 e 1,1 não sejam mais usados.

Você também pode usar o Internet Explorer para testar conexões de TLS para serviços Web do Skype for Business Server 2015 após a desabilitação do TLS 1,0 e do TLS 1,1.

1. Inicie o Internet Explorer.
2. Selecione **ferramentas** > **Opções da Internet**.
3. Selecione a guia **avançado** .
4. Em **configurações**, role até a parte inferior.
5. Verifique se o TLS 1,0, o TLS 1,1 e o TLS 1,2 estão habilitados.
6. Procure a URL do serviço Web interno do pool do SfB 2015 (deve se conectar com êxito).
7. Volte para o Internet Explorer e desabilite a opção para **usar somente TLS 1,2** .
8. Procure a URL do serviço Web interno do pool do SfB 2015 novamente (não deve se conectar).

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Cenários de implantação avançados

Como alguns pré-requisitos de dependência são necessários para dar suporte a TLS 1,2 no Skype for Business ser 2015, a instalação a partir da mídia RTM falhará em qualquer sistema em que o TLS 1,0 e o 1,1 tenham sido desabilitados.

**Implantar novos servidores de edição padrão ou pools da edição Enterprise após a desabilitação do TLS 1,0 e do 1,1 no seu ambiente.**

**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Observe que estamos atualizando SmartSetup para acomodar os binários do SQL atualizados em uma futura RECOR e atualizar este artigo no futuro.

**Opção 2:** Pré-instalar instâncias do SQL locais (RTCLOCAL e LYNCLOCAL)

1. Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64. exe) para a pasta local no FE. Digamos que o caminho da pasta <SQL_FOLDER_PATH>.
2. Inicie o PowerShell ou prompt de comando e navegue até <SQL_FOLDER_PATH>.
3. Crie a instância do SQL RTCLOCAL executando o comando abaixo. Aguarde até que o SQLEXPR_x64. exe termine antes de continuar:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automatizar
1. Crie a instância do SQL LYNCLOCAL executando o comando abaixo. Aguarde até que o SQLEXPR_x64. exe termine antes de prosseguir para a próxima etapa:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic
1. Executar a instalação do Skype for Business Server 2015 RTM.
2. Siga as etapas restantes na seção pré-requisitos acima.

**Opção 3:** Você também pode substituir manualmente os binários em um diretório de mídia de instalação local da seguinte maneira:

1. [Instalar pré-requisitos para o Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Instale o .NET 4,7: 
      - **Observação:** Primeiro, introduzimos o suporte para o .NET 4,7 no Skype for Business Server 2015 CU5 (6.0.9319.281). Portanto, em etapas mais adiante abaixo, atualizaremos os componentes principais antes da instalação principal.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167. 
      - Referência: [software que deve ser instalado antes de uma implantação do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiar arquivos/pastas ISO: 
    - Com a ISO do Skype for Business Server 2015 anexada, abra o diretório raiz da unidade em que está conectado (ex: D\) : no explorador de arquivos).
    - Copiar todas as pastas e arquivos para uma pasta em um disco local (por exemplo: C:\SkypeForBusiness2015ISO).
    - **Observação:** Antes de instalar os componentes, alguns arquivos precisarão ser atualizados para dar suporte ao TLS 1,2.
4. Substituir pacotes MSI/EXE: 
    - Substitua os pacotes MSI e EXE existentes na pasta/Setup/AMD64/da mídia de instalação no computador local.
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Renomeie para SQLEXPR_x64 na máquina local e substitua o arquivo existente na pasta Setup/AMD64/da mídia de instalação.
    - Cliente SQL Native:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Observação:** Renomeie isso se necessário para sqlncli. msi e substitua o arquivo existente que existe na mídia de instalação/amd64/pasta da mídia de instalação.
    - Objetos de gerenciamento do SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Observação:** O pacote de recursos terá muitos itens que podem ser baixados. Selecione para baixar o SharedManagementObjects. msi apenas.
        - **Observação:** Substitua o arquivo existente que existe na mídia de instalação/amd64/pasta da mídia de instalação.
    - Tipos CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Observação:** O pacote de recursos terá muitos itens que podem ser baixados. Selecione para baixar o CQLSysClrTypes. msi somente
        - **Observação**: substitua o arquivo existente que existe na pasta Setup/AMD64/da mídia de instalação.
5. Instale os componentes principais: 
    - Execute setup. exe a partir da pasta Setup/AMD64/da mídia de instalação. Siga as instruções para instalar os componentes principais
    - Feche os componentes principais.
6. Atualize os componentes principais: 
    - Baixe o instalador da atualização do Skype for Business.
    - Execute o instalador para atualizar os componentes principais e instalar os contadores de desempenho.
    - **Observação:** Desde o lançamento do CU6HF2, o recurso de atualização automática atualmente só será instalado no CU6. Portanto, o atualizador deve ser executado separadamente para atualizar os componentes principais para o 6.0.9319.516.
    - Referenciehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Instalar ferramentas administrativas (opcional): 
    - Isso instalará os tipos de Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR para SQL Server 2014 (x64) usando os arquivos atualizados. Além disso, o construtor de topologia do Skype for Business Server 2015 e o painel de controle estarão disponíveis no computador local.
8. Instale o repositório de configuração local (etapa 1): 
     - Abra o assistente de implantação, clique em instalar ou atualizar o sistema do Skype for Business Server e clique em **executar** na etapa 1: instalar o repositório de configuração local.
     - Clique em **Avançar** na caixa de diálogo **instalar repositório de configuração local** .
     ![Caixa de diálogo instalar repositório de configuração local](../../media/local-configuration-store.png)
     - Examine os resultados e certifique-se de que o status da tarefa seja concluído. Examine o arquivo de log resultante clicando em **Exibir log**.
     ![O status da tarefa é exibido como concluído](../../media/local-configuration-task-completed.png)
     - Clique em **Concluir**.
9. Configurar ou remover componentes do Skype for Business Server (etapa 2):
    - Abra o assistente de implantação, clique em **instalar ou atualizar o sistema do Skype for Business Server**e clique em **executar** na etapa 2: configurar ou remover componentes do Skype for Business Server
    - Clique em **Avançar** na caixa de diálogo Configurar componentes do Skype for Business Server.
    ![a janela Configurar o Skype for Business Server Components](../../media/set-up-skype-for-business-server-components-window.png)
    - Examine o log usando o log de exibição e valide se a configuração foi concluída sem problemas. 
    - Clique em **Concluir**.
10. Prossiga com a instalação e a configuração adicionais conforme necessário (você pode retomar os procedimentos de instalação normal neste ponto).
