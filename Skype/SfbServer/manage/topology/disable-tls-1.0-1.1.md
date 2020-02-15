---
title: Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: Prepare-se e implemente a desabilitação de TLS 1,0 e 1,1 em seus ambientes.'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012744"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015

O objetivo deste artigo é fornecer as diretrizes necessárias para preparar e implementar a desabilitação de TLS 1,0 e 1,1 em seus ambientes. Esse processo requer planejamento e preparação abrangentes. Revise cuidadosamente todas as informações deste artigo ao fazer seu plano para desabilitar o TLS 1,0 e 1,1 para sua organização. Observe que há muitas dependências externas e condições de conectividade que podem ser impactadas desabilitando o TLS 1.0/1.1, portanto, o planejamento e o teste extensivos são garantidos.

## <a name="in-this-article"></a>Neste artigo

- [Plano de fundo e escopo](#background)
- [Pré-requisitos e processo](#prerequisites-and-process)
- [Cenários de implantação avançada](#advanced-deployment-scenarios)

## <a name="background"></a>Segundo plano

Os principais drivers de fornecimento de TLS 1,0 e 1,1 desabilitar o suporte para o Skype for Business Server no local são os padrões de segurança do setor de cartão de pagamento PCI e os requisitos de padrões federais de processamento de informações. É [possível encontrar mais](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)informações sobre os requisitos de PCI.  A Microsoft não pode fornecer orientações sobre a necessidade ou não de sua organização para cumprir estes ou outros requisitos. Você deve determinar se é necessário desabilitar o TLS 1,0 e/ou 1,1 em seus ambientes.

A Microsoft produziu um White paper sobre o TLS disponível [aqui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)e também recomendamos a leitura em segundo plano disponível neste [blog do Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Escopo de capacidade de suporte

O *escopo* se refere aos limites de capacidade de suporte. *Totalmente testado e com suporte* significa que oferecemos suporte para a desabilitação de TLS 1,0 e 1,1 para as versões de produto listadas. *Sendo investigado no momento* significa apenas isso; Estamos investigando ativamente os produtos em escopo para habilitar o suporte a TLS. *Fora do escopo* significa que essas versões do produto não dão suporte à desabilitação de TLS 1,0 ou 1,1 e não funcionarão, com exceções anotadas.

### <a name="fully-tested-and-supported-servers"></a>Servidores totalmente testados e com suporte

- Skype for Business Server 2019 CU1 17.0.2046.123 (junho de 2019) ou superior
- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior no Windows Server 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização substituindo), 2012 R2 ou 2016.
- Atualizado no local o Skype for Business Server 2015, com o CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização de substituição) ou 2012 R2.
- Conectividade do Exchange e Outlook Web App com o Exchange Server 2010 SP3 RU19 ou superior, orientação [aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Aparelho de filial persistente (SBA) com o Skype for Business Server 2015 CU6 HF2 ou superior (confirme com seu fornecedor que eles empacotaram as atualizações do apropriado e foram disponibilizados para o seu dispositivo)
- Servidor de ramificação persistente (SBS) com o Skype for Business Server 2015 CU6 HF2 ou superior
- **Somente função de borda**do Lync Server 2013, isso ocorre porque a função de borda não tem uma dependência no Windows Fabric 1,0.

### <a name="fully-tested-and-supported-clients"></a>Clientes totalmente testados e com suporte

- Lync 2013 (Skype for Business) Desktop Client, MSI e C2R, incluindo o [15.0.5023.1000 básico ou superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Cliente de área de trabalho do Skype for Business 2016, MSI [16.0.4678.1000 ou superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluindo básico
- Skype for Business 2016 clique para executar exigir as atualizações de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Mensal e com destino semestral, 16\.0\.9126\.2152 ou superior
    - Canal semianual e adiado, 16\.0\.8431\.2242 ou superior
- Skype for Business no Mac 16,15 ou superior
- Skype for Business para iOS e Android 6,19 ou superior
- Salas do Microsoft Teams (anteriormente conhecido como Skype Room System v2 SRS v2) 4.0.64.0 (dezembro de 2018) ou superior
- Atualização do Surface Hub para Team Edition com base no KB4499162 (maio de 2019, compilação de sistema operacional 15063,1835) ou superior
- Skype Web App 2015 CU6 HF2 ou superior (fornecido com o servidor)

### <a name="currently-being-investigated"></a>Sendo investigado no momento

- Painel de qualidade de chamada (nova instalação após TLS 1,0, 1,1 foram desabilitadas, veja abaixo) *
 
### <a name="out-of-scope"></a>Fora do escopo

Exceto onde observado, os seguintes produtos não estão no escopo para TLS 1.0/1.1 desabilitam o suporte e não funcionarão em um ambiente em que o TLS 1,0 e 1,1 foram desabilitados. O que isso significa: se você ainda utilizar servidores ou clientes fora do escopo, deverá atualizar ou remover estes se precisar desabilitar o TLS 1.0/1.1 em qualquer lugar em sua implantação local do Skype for Business Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 ou inferior
- Lync para Mac 2011
- Lync 2013 para Mobile-iOS, iPad, Android ou Windows Phone
- Cliente da Windows Store "MX" do Lync
- Sistema de salas do Lync (conhecido como SRSv1). O LRS atingiu o fim do suporte em 9 de outubro de 2018 e não será atualizado para suportar o TLS 1,2.
- Todos os clientes do Lync 2010
- Lync Phone Edition – orientações atualizadas [aqui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- SBA (aparelho de filial persistente com base em 2013) ou servidor de filial persistente (SBS)
- Cloud Connector Edition (CCE)
- Skype for Business para Windows Phone

### <a name="exceptions"></a>Exceções

#### <a name="lync-server-2013"></a>Lync Server 2013

O Lync Server 2013 tem uma dependência no Windows Fabric versão 1,0.  Na fase de design do Lync Server 2013, o Windows Fabric 1,0 foi escolhido por sua arquitetura distribuída e nova, para fornecer replicação, alta disponibilidade e tolerância a falhas.  Com o tempo, tanto o Skype for Business Server quanto o Windows Fabric melhoraram muito essa arquitetura conjunta com um novo design significativo nas versões subsequentes.  O servidor atual do Skype for Business 2015 usa o Windows Fabric 3,0, por exemplo.

Infelizmente, o Windows Fabric 1,0 não **oferece suporte a TLS 1,2.  No entanto, atualizaremos o Lync Server 2013 para funcionar com TLS 1,2**. Isso será disponibilizado na próxima atualização cumulativa para o Lync Server 2013.  Estamos fornecendo suporte a TLS 1,2 para habilitar a coexistência, migração, Federação e cenários híbridos.

Se sua organização for necessária para desabilitar o TLS 1,0 e 1,1, e você estiver usando o Lync Server 2013, recomendamos que você inicie o processo de planejamento, com a possibilidade de que você possa ter a atualização in-loco ou migrar lado a lado (novos pools, mover usuários) para o Skype para Business Server 2015 ou superior.  Ou talvez você queira acelerar a migração para o Skype for Business online.

#### <a name="call-quality-dashboard"></a>Painel de qualidade da chamada

No momento, o painel de qualidade de chamada local tem uma dependência no TLS 1,0 durante a nova instalação (primeira vez em que é feita a instalação em seus ambientes locais).  No momento, estamos investigando esse problema e planejamos lançar uma correção em um futuro próximo.  Se você estiver planejando instalar o CQD e também desabilitar o TLS 1,0, recomendamos concluir a instalação do CQD primeiro e, em seguida, prosseguir com o TLS 1,0 desabilitando.

#### <a name="third-party-devices"></a>Dispositivos de terceiros

Em dispositivos de terceiros, como telefones 3PIP, conferência de vídeo, proxies reverso e balanceadores de carga, certifique-se de validar o suporte a TLS 1,2, teste cuidadosamente e entre em contato com o fornecedor, se necessário.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considerações de Federação ao desabilitar o TLS 1.0/1.1 em servidores de borda

Você deve planejar cuidadosamente e considerar o impacto de desabilitar o TLS 1.0/1.1 nos servidores de borda.  Depois que o TLS 1,0 e 1,1 estiverem desabilitados, você poderá achar que outras organizações não poderão ser federadas com sua organização.

Você pode optar por manter o TLS 1.0/1.1 habilitado em seus servidores de borda para manter a compatibilidade com versões anteriores de sistemas externos não corrigidos (SfB 2015, Lync 2013) ou mais antigos (2010).

A Microsoft não pode fornecer conselhos ou recomendações sobre se a rede de borda (ou qualquer rede) está ou não no padrão PCI; Isso deve ser determinado pela empresa individual.

O Skype for Business Online é capaz de permitir o TLS 1,2 hoje, portanto, não é esperado nenhum impacto no híbrido/Federação online.

PIC (conectividade de IM pública) para o serviço de consumidor do Skype: não esperamos desabilitar o TLS 1.0/1.1 para impactar a [conectividade do Skype](../../deploy/deploy-skype-connectivity.md); Os gateways PIC da Microsoft já são compatíveis com o TLS 1,2.

## <a name="prerequisites-and-process"></a>Pré-requisitos e processo

Exceto quando observado acima, depois que o TLS 1,0 e 1,1 forem desabilitados servidores fora do escopo, os clientes e dispositivos funcionarão mais corretamente ou de qualquer forma. Isso pode significar que você precisa pausar e aguardar orientações atualizadas da Microsoft. Quando estiver satisfeito com a necessidade de atender a todos os requisitos e ter um plano para lidar com as lacunas, continue.

Em um nível alto, enquanto o Skype for Business Server 2019 estiver pronto para o procedimento a ser instalado, o Skype for Business Server 2015 exigirá que você instale o CU9, aplicando atualizações de pré-requisito ao .NET e ao SQL, implantando chaves de registro de pré-requisito e, por fim, um arredondamento de atualizações de configuração de so (ou seja, desabilitar o TLS 1,0 e 1,1 por meio da importação de arquivo do registro). É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo o Skype for Business Server 2015 CU6 HF2, antes de desabilitar o TLS 1,0 e 1,1 em qualquer servidor do seu ambiente. Todo o Skype for Business Server, incluindo função de borda e backends SQL, requer as atualizações. Além disso, certifique-se de que todos os clientes com suporte (em escopo) foram atualizados para as versões mínimas necessárias. Não se esqueça também de atualizar as estações de trabalho de gerenciamento.

Queremos seguir a ordem usual de operações de "Inside Out" para atualizar os servidores do Skype for Business. Trate pools de diretores, chat persistente e pools emparelhados da mesma maneira que você faria normalmente. O pedido e os métodos para atualização são abordados [aqui](topology.md) e [aqui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processo de alto nível

1. Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.
2. Faça backup e preserve uma cópia do registro exportado em cada servidor individual a ser atualizado. Não é possível compartilhar registros entre servidores; Eles contêm chaves exclusivas baseadas em máquina.
3. Atualize todos os servidores do Skype for Business 2015 para o CU9 ou superior. Para o Skype for Business Server 2019, atualize para o CU1 ou superior.
4. Instale todos os pré-requisitos para todos os servidores.
5. Implantar chaves de registro de pré-requisito.
6. Verifique se todos os clientes no escopo estão atualizados.
7. Desabilite o TLS 1,0 e 1,1 via importação do registro.
8. Validar que as cargas de trabalho estão funcionando conforme o esperado.
    - Se forem encontrados problemas, solucionar e resolver, ou
    - Restaure o registro da etapa 2 para reabilitar o TLS 1,0 e 1,1
9. Valide que apenas o TLS 1,2 está sendo usado.

### <a name="install-prerequisites-to-all-servers"></a>Instalar pré-requisitos para todos os servidores

Uma atualização de dependência extensiva é necessária antes de começar a desabilitar o TLS 1,0 e 1,1 no nível do sistema operacional em suas implantações de 2015 do Skype for Business Server. Veja a seguir as versões mínimas que podem dar suporte a TLS 1,2. Implante todas as atualizações de pré-requisito em cada Skype for Business Server em seu ambiente antes de começar a desabilitar o TLS 1,0 e 1,1.

- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) ou superior com o SchUseStrongCrypto habilitado no registro (fornecido abaixo)
- O SQL deve ser atualizado em todos os servidores do Skype for Business 2015 e de back-ends. Atualize o pool de SQL da Enterprise Edition primeiro e depois o respectivo FEs. 
    - [SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)ou superior/sql Server 2012 SP2 + atualização cumulativa 16 ou superior/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)ou superior/SQL Server 2014 SP2
     - [SQL Server Native Client para SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)ou superior
     - [Objetos de gerenciamento compartilhado para o SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes para o SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Etapas básicas para instalar os pré-requisitos, em ordem recomendada de operações

1. Instale a atualização do Skype for Business Server CU9 em todos os servidores. 
    1. Instale a atualização dos componentes usando o atualizador.
    2. Atualizar bancos de dados de acordo com procedimentos documentados. Para o Skype for Business Server 2015, confira KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Validar a funcionalidade do produto na implantação antes de prosseguir com outras alterações.
2. Baixe o instalador offline do .NET 4,7. 
    1. Indicação[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.
    3. Indicação[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition):```Stop-CsWindowsService```
    5. Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    6. Execute o pacote de instalação.
    7. Reinicialize o servidor.
3. Atualize o SQL Express 2014 em todos os servidores. 
    1. Indicação[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Baixar o SQL 2014 SP2 
        - Indicação[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copie a mídia de instalação para uma pasta no servidor (ex: C:\ 01_2014SqlSp2)
    4. Garantir que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end 
        - Ex (Standard Edition):```Stop-CsWindowsService```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    5. Abrir um prompt de comando do administrador e atualizar todos os componentes e instâncias instalados 
        - Exemplo: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. Atualize o SQL Native Client. 
    1. Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Baixar do[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Verifique se os serviços do Skype for Business Server 2015 estão interrompidos no servidor front-end. 
        - Ex (Standard Edition):```Stop-CsWindowsServices```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    4. Interromper a execução das instâncias SQL instaladas 
        - Ex```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Standard Edition apenas):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Instale a atualização.
5. Atualize o ODBC Driver 11 para SQL Server para incluir suporte para TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Baixe o [ODBC Driver 11 para SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.
        - Exemplo (edição Standard):```Stop-CsWindowsService```
        - Exemplo (Enterprise Edition):```Invoke-CsComputerFailover```
    3. Instale a atualização.
6. Implantar chaves de registro de pré-requisito.

### <a name="pre-requisite-registry-keys"></a>Chaves de registro de pré-requisito

Copie/cole o teste a seguir no bloco de notas e renomeie o TLSPreReq. reg ou um nome de sua escolha e, em seguida, importe:

```console
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

Para o SQL back ends para os pools Enterprise Edition, os pré-requisitos e a desabilitação de TLS devem ser tratados como qualquer atualização SQL ou de so; consulte:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Embora o aplicativo de pré-requisito e as etapas de desabilitação de TLS possam ser combinados, é altamente recomendável que todos os pré-requisitos sejam aplicados antes de prosseguir com a desabilitação de TLS 1,0 e 1,1 no nível do sistema operacional. A abordagem de práticas recomendadas seria preparar o ambiente implantando todos os pré-requisitos, Validando que as cargas de trabalho funcionaram corretamente e conforme o esperado e, em seguida, prosseguindo com o TLS 1.0/1.1 desabilitado posteriormente.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Desabilitar o TLS 1,0 e 1,1 via importação do registro

Antes de prosseguir com as próximas etapas, *certifique-se de ter concluído todos os pré-requisitos e os servidores do Skype for Business atualizados*.

Copie o seguinte texto em um arquivo do bloco de notas e renomeie-o **TLSDisable. reg**:

```console
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

Importe o arquivo. reg em cada servidor que você deseja desabilitar o TLS 1,0 e 1,1. Reinicialize o servidor. Depois que os serviços voltarem online, vá para o próximo servidor. A abordagem para pools Enterprise Edition é o mesmo que você faria para qualquer atualização de sistema operacional.

Você pode ter notado que estamos fazendo mais do que simplesmente desabilitando o TLS 1,0 e 1,1 aqui. Estamos dando suporte à reordenação do pacote de codificação (conforme mostrado acima) e à desabilitação de algumas cifras fracas mais antigas. Esta é a primeira vez que suportamos oficialmente essas alterações para a API de criptografia e SCHANNEL no Skype for Business Server, e é importante observar que essas alterações são as únicas que suportamos e testaram no momento. Podemos considerar configurações adicionais no futuro, mas por enquanto, não modifique o arquivo de importação do registro em sua implementação.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Validar que as cargas de trabalho estão funcionando conforme o esperado

Após o TLS 1,0 e 1,1 ter sido desabilitado em seu ambiente, verifique se todas as cargas de trabalho principais estão funcionando conforme o esperado, como a presença de mensagens instantâneas &, chamadas P2P, Enterprise Voice, etc.

**Validar somente TLS 1,2 está sendo usado**

Faça com que sua equipe de segurança execute uma nova auditoria de tráfego do Skype for Business para garantir que os protocolos mais antigos TLS 1,0 e 1,1 não estejam mais em uso.

Como alternativa, você pode usar o Internet Explorer para testar conexões TLS para serviços Web do Skype for Business Server 2015 após o TLS 1,0 e o TLS 1,1 terem sido desabilitados.

1. Inicie o Internet Explorer.
2. Selecione **ferramentas** > **Opções da Internet**.
3. Selecione a guia **avançado** .
4. Em **configurações**, role até o final.
5. Verifique se o TLS 1,0, TLS 1,1 e TLS 1,2 estão habilitados.
6. Procure a URL do serviço Web interno do seu pool do SfB 2015 (deve se conectar com êxito).
7. Volte para o Internet Explorer e desabilite a opção para **usar somente TLS 1,2** .
8. Procure a URL do serviço Web interno do pool do SfB 2015 novamente (não deve se conectar).

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Cenários de implantação avançada

Como alguns pré-requisitos de dependência são necessários para dar suporte a TLS 1,2 no Skype for Business ser 2015, a instalação da mídia RTM falhará em qualquer sistema em que o TLS 1,0 e 1,1 tenham sido desabilitados.

**Implantar novos servidores Standard Edition ou pools Enterprise Edition após o TLS 1,0 e 1,1 ter sido desabilitado em seu ambiente.**

**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Observe que estamos atualizando o SmartSetup para acomodar os binários do SQL atualizados em uma futura CU e atualizar este artigo no futuro.

**Opção 2:** Pré-instalar instâncias do SQL locais (RTCLOCAL e LYNCLOCAL)

1. Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64. exe) para a pasta local no FE. Digamos que o caminho da pasta <SQL_FOLDER_PATH>.
2. Inicie o PowerShell ou prompt de comando e navegue até <SQL_FOLDER_PATH>.
3. Crie a instância do SQL RTCLOCAL executando o comando a seguir. Aguarde até que o SQLEXPR_x64. exe seja concluído antes de prosseguir:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\administradores"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automatizi
1. Crie a instância do SQL LYNCLOCAL executando o comando a seguir. Aguarde até que o SQLEXPR_x64. exe seja concluído antes de prosseguir para a próxima etapa:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\administradores"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic
1. Executar a instalação do Skype for Business Server 2015 RTM.
2. Siga as etapas restantes da seção pré-requisitos acima.

**Opção 3:** Você também pode substituir manualmente os binários em um diretório de mídia de instalação local da seguinte maneira:

1. [Instalar pré-requisitos para o Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Instale o .NET 4,7: 
      - **Observação:** Primeiro, apresentamos suporte para o .NET 4,7 no Skype for Business Server 2015 CU5 (6.0.9319.281). Portanto, nas etapas posteriores abaixo, atualizaremos os componentes principais antes da instalação principal.
      - Baixar: https://www.microsoft.com/download/details.aspx?id=55167. 
      - Referência: [software que deve ser instalado antes da implantação do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiar arquivos/pastas ISO: 
    - Com o ISO do Skype for Business Server 2015 conectado, abra o diretório raiz da unidade à qual ele está conectado (ex: D\) : no explorador de arquivos.
    - Copiar todas as pastas e arquivos para uma pasta em um disco local (ex: C:\SkypeForBusiness2015ISO).
    - **Observação:** Antes de instalar os componentes, alguns arquivos precisarão ser atualizados para o suporte do TLS 1,2.
4. Substituir pacotes MSI/EXE: 
    - Substitua os pacotes MSI e EXE existentes na pasta/Setup/AMD64/da mídia de instalação no computador local.
    - SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167 
        - Renomeie como SQLEXPR_x64 no computador local e substitua o arquivo existente na instalação/amd64/pasta da mídia de instalação.
    - SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402 
        - **Observação:** Renomeie-o se necessário para sqlncli. msi e substitua o arquivo existente que existe na mídia de instalação/amd64/pasta.
    - Objetos de gerenciamento do SQL:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Observação:** O Feature Pack terá muitos itens que podem ser baixados. Selecione para baixar o SharedManagementObjects. msi apenas.
        - **Observação:** Substitua o arquivo existente que existe na pasta Setup/AMD64/da mídia de instalação.
    - Tipos CLR SQL:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Observação:** O Feature Pack terá muitos itens que podem ser baixados. Selecione para baixar o CQLSysClrTypes. msi somente
        - **Observação**: substitua o arquivo existente que existe na pasta Setup/AMD64/da mídia de instalação.
5. Instale os componentes principais: 
    - Execute setup. exe a partir da pasta Setup/AMD64/da mídia de instalação. Siga as instruções para instalar os componentes principais
    - Feche os componentes principais.
6. Atualizar componentes principais: 
    - Baixe o instalador de atualização do Skype for Business.
    - Execute o instalador para atualizar os componentes principais e instalar os contadores de desempenho.
    - **Observação:** A partir da versão do CU6HF2, o recurso de atualização automática atualmente só instalará até o CU6. Portanto, o atualizador deve ser executado separadamente para atualizar os componentes principais para o 6.0.9319.516.
    - Indicaçãohttps://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Instalar ferramentas administrativas (opcional): 
    - Isso instalará o Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR Types for SQL Server 2014 (x64) usando os arquivos atualizados. Além disso, o construtor de topologias do Skype for Business Server 2015 e o painel de controle estarão disponíveis na máquina local.
8. Instale o repositório de configuração local (etapa 1): 
     - Abra o assistente de implantação, clique em instalar ou atualizar o sistema do Skype for Business Server e clique em **executar** na etapa 1: instalar o repositório de configuração local.
     - Clique em **Avançar** na caixa de diálogo **instalar repositório de configuração local** .
     ![Caixa de diálogo instalar repositório de configuração local](../../media/local-configuration-store.png)
     - Revise os resultados e verifique se o status da tarefa está concluído. Examine o arquivo de log resultante clicando em **Exibir log**.
     ![O status da tarefa é exibido como concluído](../../media/local-configuration-task-completed.png)
     - Clique em **Concluir**.
9. Configurar ou remover componentes do Skype for Business Server (etapa 2):
    - Abra o assistente de implantação, clique em **instalar ou atualizar o sistema do Skype for Business Server**e clique em **executar** na etapa 2: configurar ou remover componentes do Skype for Business Server
    - Clique em **Avançar** na caixa de diálogo Configurar componentes do Skype for Business Server.
    ![a janela configurar componentes do Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Revise o log usando o log de exibição e valide se a instalação foi concluída sem problemas. 
    - Clique em **Concluir**.
10. Prossiga com a instalação e a configuração adicionais, conforme necessário (você pode retomar os procedimentos de instalação normais neste ponto).
