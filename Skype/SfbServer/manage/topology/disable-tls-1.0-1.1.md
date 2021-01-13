---
title: Desabilitar o TLS 1.0/1.1 no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: prepare e implemente a desabilitação do TLS 1.0 e 1.1 em seus ambientes.'
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826391"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Desabilitar o TLS 1.0/1.1 no Skype for Business Server 2015

O objetivo deste artigo é fornecer as orientações necessárias para que você se prepare e implemente a desabilitação do TLS 1.0 e 1.1 em seus ambientes. Esse processo requer planejamento e preparação abrangentes. Revise cuidadosamente todas as informações neste artigo ao planejar desabilitar o TLS 1.0 e 1.1 para sua organização. Observe que há muitas dependências externas e condições de conectividade que podem ser impactadas desabilitando o TLS 1.0/1.1, portanto, é preciso planejar e testar extensivamente.

## <a name="in-this-article"></a>Neste artigo

- [Plano de fundo e escopo](#background)
- [Pré-requisitos e processo](#prerequisites-and-process)
- [Cenários de implantação avançada](#advanced-deployment-scenarios)

## <a name="background"></a>Histórico

Os principais fatores para o fornecimento do TLS 1.0 e 1.1 desabilitam o suporte para o Skype for Business Server Local são o Conselho de Padrões de Segurança PCI (Payment Card Industry) e os requisitos dos Padrões Federais de Processamento de Informações. Mais informações sobre os requisitos de PCI podem ser [encontradas aqui.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)  A Microsoft não pode fornecer orientações sobre se a sua organização deve ou não cumprir esses ou outros requisitos. Você deve determinar se é necessário desabilitar o TLS 1.0 e/ou 1.1 em seus ambientes.

A Microsoft produziu um white paper sobre o TLS disponível [aqui,](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)e também recomendamos a leitura de plano de fundo disponível neste [blog do Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)

## <a name="supportability-scope"></a>Escopo de suporte

*O escopo* refere-se aos limites de suporte. *Totalmente testado e com* suporte significa que damos suporte total e testamos a desabilitação do TLS 1.0 e 1.1 para as versões do produto listadas. *Atualmente sendo investigado significa* apenas que; Estamos investigando ativamente para colocar esses produtos no escopo para que o TLS desabilite o suporte. *Fora do* escopo significa que essas versões do produto não suportam a desabilitação do TLS 1.0 ou 1.1 e não funcionarão, com exceções notadas.

### <a name="fully-tested-and-supported-servers"></a>Servidores totalmente testados e com suporte

- Skype for Business Server 2019 CU1 17.0.2046.123 (junho de 2019) ou superior
- Skype for Business Server 2015 CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização de sobressedida), 2012 R2 ou 2016.
- Skype for Business Server 2015 atualizado in-place, com CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização de sobressedido) ou 2012 R2.
- Conectividade do Exchange e Outlook Web App com o Exchange Server 2010 SP3 RU19 ou superior, [orientações aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Aparelho de Filial Confiável (SBA) com Skype for Business Server 2015 CU6 HF2 ou superior (confirme com seu fornecedor que eles empacotam as atualizações apropriadas e foram disponibilizadas para seu dispositivo)
- Servidor de FilialVivável (SBS) com Skype for Business Server 2015 CU6 HF2 ou superior
- Somente função de borda do Lync Server 2013 , isso acontece porque a função de Borda não tem uma dependência no Windows Fabric 1.0.

### <a name="fully-tested-and-supported-clients"></a>Clientes totalmente testados e com suporte

- Lync 2013 (Skype for Business) Desktop Client, MSI e C2R, incluindo Basic [15.0.5023.1000 ou superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 ou superior,](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)incluindo Básico
- O Clique para Executar do Skype for Business 2016 requer as atualizações de [abril de 2018:](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 
    - Mensal e Semi-Annual Direcionado, 16 \. 0 \. 9126 \. 2152 ou superior
    - Semi-Annual e Canal Adiado, 16 \. 0 \. 8431 \. 2242 ou superior
- Skype for Business no Mac 16.15 ou superior
- Skype for Business para iOS e Android 6.19 ou superior
- Salas do Microsoft Teams (anteriormente conhecidas como Sistema de Salas Skype V2 SRS V2) 4.0.64.0 (dezembro de 2018) ou superior
- Atualização do Surface Hub para a edição Team com base no KB4499162 (maio de 2019, com build 15063.1835 do sistema operacional) ou superior
- Skype Web App 2015 CU6 HF2 ou superior (acompanha o Servidor)

### <a name="currently-being-investigated"></a>Atualmente sendo investigado

- Painel de Qualidade da Chamada (nova instalação após o TLS 1.0, 1.1 ter sido desabilitado, veja abaixo)*
 
### <a name="out-of-scope"></a>Fora do escopo

Exceto quando anotou, os produtos a seguir não estão no escopo para o TLS 1.0/1.1 desabilitam o suporte e não funcionarão em um ambiente onde o TLS 1.0 e 1.1 foram desabilitados. Isso significa que, se você ainda utilizar servidores ou clientes fora do escopo, deverá atualizá-los ou removê-los se precisar desabilitar o TLS 1.0/1.1 em qualquer lugar na implantação local do Skype for Business Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 ou inferior
- Lync para Mac 2011
- Lync 2013 para celular - iOS, iPad, Android ou Windows Phone
- Cliente Lync "MX" da Windows Store
- Sistema de Sala do Lync (ou seja, SRSv1). O LRS atingiu o fim do suporte em 9 de outubro de 2018 e não será atualizado para dar suporte ao TLS 1.2.
- Todos os clientes do Lync 2010
- Lync Phone Edition - orientações [atualizadas aqui.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)
- Aparelho de Filial Sobrevivência (SBA) baseado em 2013 ou SBS (Servidor de Filial Survivable)
- Cloud Connector Edition (CCE)
- Skype for Business for Windows Phone

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

O Lync Server 2013 depende do Windows Fabric versão 1.0.  Na fase de design do Lync Server 2013, o Windows Fabric 1.0 foi escolhido por sua nova arquitetura distribuída atraente e atraente para fornecer replicação, alta disponibilidade e tolerância a falhas.  Com o tempo, o Skype for Business Server e o Windows Fabric melhoraram significativamente essa arquitetura conjunta com um re-design significativo em versões subsequentes.  O Skype for Business Server 2015 server atual usa o Windows Fabric 3.0, por exemplo.

Infelizmente, o Windows Fabric 1.0 **não dá suporte a TLS 1.2.  No entanto, atualizaremos o Lync Server 2013 para trabalhar com o TLS 1.2.** Isso estará presente na próxima Atualização Cumulativa do Lync Server 2013.  Estamos fornecendo suporte a TLS 1.2 para habilitar a co-existência, migração, federação e cenários híbridos.

Se sua organização precisar desabilitar o TLS 1.0 e 1.1, e você usar o Lync Server 2013 no momento, recomendamos que você comece o processo de planejamento, com a possibilidade de ter que fazer uma atualização in-loco ou migrar lado a lado (novos pools, mover usuários) para o Skype for Business Server 2015 ou superior.  Ou talvez você queira acelerar a migração para o Skype for Business Online.

#### <a name="call-quality-dashboard"></a>Painel de Qualidade da Chamada

Atualmente, o Painel de Qualidade de Chamada Local depende do TLS 1.0 durante a nova instalação (instalação pela primeira vez em seus ambientes locais).  No momento, estamos investigando esse problema e planejamos lançar uma correção em um futuro próximo.  Se você estiver planejando instalar o CQD e também desabilitar o TLS 1.0, recomendamos que você conclua a instalação do CQD primeiro e continue com a desabilitação do TLS 1.0.

#### <a name="skype-for-business-sdn-manager"></a>Gerenciador SDN do Skype for Business

O Gerenciador de SDN do Skype for Business usando o SQL tem uma dependência do TLS 1.0 durante a nova instalação. Se você planeja instalar o Gerenciador de SDN do Skype for Business usando um banco de dados do SQL e também desabilitar o TLS 1.0, recomendamos concluir o Gerenciador de SDN do Skype for Business primeiro e, em seguida, continuar com a desabilitação do TLS 1.0. Caso o TLS 1.0 tenha sido desabilitado antes da instalação, você deve habilitar temporariamente o TLS 1.0 de volta no servidor back-end do SQL Server que será usado para hospedar o banco de dados SQL do Gerenciador de SDN do Skype for Business.

#### <a name="third-party-devices"></a>Dispositivos de terceiros

Em dispositivos de terceiros, como telefones 3PIP, Videoconferência, Proxies Reversos e Balanceadores de Carga, certifique-se de validar a capacidade de suporte do TLS 1.2, teste cuidadosamente e contate o fornecedor, se necessário.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considerações de federação ao desabilitar o TLS 1.0/1.1 em servidores de Borda

Você deve planejar cuidadosamente e considerar o impacto da desabilitação do TLS 1.0/1.1 em seus servidores de Borda.  Depois que o TLS 1.0 e 1.1 são desabilitados, você pode descobrir que outras organizações não podem mais federar com sua organização.

Você pode optar por manter o TLS 1.0/1.1 habilitado em seus servidores de Borda para manter a compatibilidade com versões mais antigas com sistemas externos não patches (SfB 2015, Lync 2013) ou mais antigos (2010).

A Microsoft não pode fornecer conselhos ou recomendações sobre se a rede de Borda (ou qualquer rede) está ou não no padrão PCI; que deve ser determinado pela empresa individual.

O Skype for Business Online é capaz de ter o TLS 1.2 hoje, portanto, não se espera nenhum impacto no híbrido/federação com o Online.

PIC (Conectividade pública de IM) para o serviço de consumidor do Skype: não esperamos que a desabilitação do TLS 1.0/1.1 acarta a conectividade do [Skype;](../../deploy/deploy-skype-connectivity.md) Os Gateways de PIC da Microsoft já têm capacidade para TLS 1.2.

## <a name="prerequisites-and-process"></a>Pré-requisitos e processo

Exceto quando mencionado acima, uma vez que os TLS 1.0 e 1.1 estão desabilitados para servidores fora do escopo, os clientes e dispositivos funcionarão mais corretamente ou de forma alguma. Isso pode significar que você precisa pausar e aguardar por orientações atualizadas da Microsoft. Quando tiver a satisfação de atender a todos os requisitos e tiver um plano para solucionar lacunas, prossiga.

Em um nível alto, enquanto o Skype for Business Server 2019 está pronto para o procedimento durante a instalação, o Skype for Business Server 2015 exigirá que você instale a CU9, aplicando atualizações de pré-requisitos ao .NET e SQL, implantando chaves de registro de pré-requisitos e, finalmente, uma série separada de atualizações de configuração do sistema operacional (ou seja, desabilitando o TLS 1.0 e 1.1 por meio da importação de arquivos do Registro). É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo o Skype for Business Server 2015 CU6 HF2, antes de desabilitar o TLS 1.0 e 1.1 em qualquer servidor em seu ambiente. Todos os servidores do Skype for Business, incluindo a função de Borda e back-end sql, exigem as atualizações. Verifique também se todos os clientes com suporte (no escopo) foram atualizados para as versões mínimas necessárias. Não se esqueça de atualizar as estações de trabalho de gerenciamento também.

Queremos seguir a ordem usual de operações de "dentro para fora" para atualizar os servidores do Skype for Business. Trate pools de Diretores, Chat Persistente e Pools Emparelhados da mesma maneira que faria normalmente. A ordem e os métodos de atualização são abordados [aqui](topology.md) e [aqui.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

### <a name="high-level-process"></a>Processo de alto nível

1. Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.
2. Fazer o back up e preservar uma cópia do Registro exportado em cada servidor individual a ser atualizado. Não é possível compartilhar registros entre servidores; eles contêm chaves exclusivas baseadas em máquina.
3. Atualize todos os servidores do Skype for Business 2015 para a CU9 ou superior. Para o Skype for Business Server 2019, atualize para CU1 ou superior.
4. Instale todos os pré-requisitos em todos os servidores.
5. Implantar chaves do Registro de pré-requisitos.
6. Certifique-se de que todos os clientes no escopo sejam atualizados.
7. Desabilite o TLS 1.0 e 1.1 por meio da importação do Registro.
8. Valide se as cargas de trabalho estão funcionando conforme o esperado.
    - Se problemas são encontrados, solução de problemas ou
    - Restaurar o Registro da etapa 2 para reabilitar o TLS 1.0 e 1.1
9. Valide que apenas o TLS 1.2 está sendo usado.

### <a name="install-prerequisites-to-all-servers"></a>Instalar pré-requisitos em todos os servidores

A atualização de dependência extensiva é necessária antes de você começar a desabilitar o TLS 1.0 e 1.1 no nível do sistema operacional em suas implantações do Skype for Business Server 2015. A seguir estão as versões mínimas que podem dar suporte a TLS 1.2. Implante todas as atualizações de pré-requisitos em todos os servidores do Skype for Business em seu ambiente antes de começar a desabilitar o TLS 1.0 e 1.1.

- Skype for Business Server 2015 CU9 6.0.9319.548 (maio de 2019) ou superior
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) ou superior com SchUseStrongCrypto habilitado no Registro (fornecido abaixo)
- O SQL deve ser atualizado em todos os servidores e back-ends do Skype for Business 2015. Atualize primeiro os back-ends SQL do pool do Enterprise Edition e, em seguida, seus respectivos FEs. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)ou superior / SQL Server 2012 SP2 + CU16 ou superior / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)ou superior / SQL Server 2014 SP2
     - [SQL Server Native Client para SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)ou superior
     - [Objetos de Gerenciamento Compartilhados para SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes para SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Etapas básicas para instalar os pré-requisitos, em ordem recomendada de operações

1. Instale a atualização do Skype for Business Server CU9 em todos os servidores. 
    1. Instale a atualização nos componentes usando o atualizador.
    2. Atualize os bancos de dados de acordo com os procedimentos documentados. Para o Skype for Business Server 2015, consulte kb [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Valide a funcionalidade do produto na implantação antes de continuar com quaisquer outras alterações.
2. Baixe o Instalador Offline do .NET 4.7. 
    1. Referência: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Verifique se os serviços do Skype for Business Server 2015 foram interrompidos no servidor front-end.
    3. Referência: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. Execute o pacote do instalador.
    7. Reinicialize o servidor.
3. Atualize o SQL Express 2014 em todos os servidores. 
    1. Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Baixar o SQL 2014 SP2 
        - Referência: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copie a mídia de instalação em uma pasta no servidor (ex: C:\01_2014SqlSp2)
    4. Garantir que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. Abra um Prompt de Comando do Administrador e atualize todos os componentes e instâncias instalados 
        - Exemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Atualize o SQL Native Client. 
    1. Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Baixar de [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Verifique se os serviços do Skype for Business Server 2015 foram interrompidos no servidor front-end. 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. Interromper a execução das instâncias SQL instaladas 
        - Por ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Por ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Somente Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Instale a atualização.
5. Atualize o driver ODBC 11 para SQL Server para incluir suporte para TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Baixe [o driver ODBC 11 para SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Verifique se os serviços do Skype for Business Server 2015 foram interrompidos no servidor front-end.
        - Exemplo (Standard Edition): ```Stop-CsWindowsService```
        - Exemplo (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. Instale a atualização.
6. Implantar chaves do Registro de pré-requisitos.

### <a name="pre-requisite-registry-keys"></a>Chaves de registro de pré-requisito

Copie/copie/copie o teste a seguir no Bloco de Notas e renomeie TLSPreReq.reg ou um nome de sua escolha e importe:

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

Para back-ends do SQL para Pools Enterprise Edition, os pré-requisitos e a desabilitação do TLS devem ser tratados como qualquer atualização do SQL ou do sistema operacional; consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Embora as etapas de desabilitação do aplicativo de pré-requisito e do TLS possam ser combinadas, recomendamos que todos os pré-requisitos sejam aplicados antes de prosseguir com a desabilitação do TLS 1.0 e 1.1 no nível do sistema operacional. A melhor abordagem seria preparar o ambiente implantando todos os pré-requisitos, validando que as cargas de trabalho funcionem corretamente e conforme o esperado e, em seguida, continuar com o TLS 1.0/1.1 desabilitar posteriormente.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Desabilitar o TLS 1.0 e 1.1 por meio da importação do Registro

Antes de prosseguir com as próximas etapas, certifique-se de ter concluído todos os *pré-requisitos* e atualizado os Servidores do Skype for Business.

Copie o texto a seguir em um arquivo do Bloco de Notas e renomeie-o **como TLSDisable.reg:**

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

Importe o arquivo .reg em cada servidor que você deseja desabilitar o TLS 1.0 e 1.1. Reinicialize o servidor. Depois que os serviços voltarem a ficar online, vá para o próximo servidor. A abordagem para Pools Enterprise Edition é a mesma que você faria para qualquer atualização do sistema operacional.

Você deve ter notado que estamos fazendo mais do que desabilitar apenas o TLS 1.0 e 1.1 aqui. Estamos dando suporte à reorganização do Cipher Suite (conforme mostrado acima) e à desabilitação de algumas codificações fracas mais antigas. Esta é a primeira vez que oficialmente suportamos essas alterações no SCHANNEL e na API de Criptografia no Skype for Business Server, e é importante observar que essas alterações são as únicas que suportamos e testamos no momento. Podemos considerar configurações adicionais no futuro, mas, por enquanto, não modifique o arquivo de importação do Registro em sua implementação.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Validar se as cargas de trabalho estão funcionando conforme o esperado

Depois que o TLS 1.0 e 1.1 tiver sido desabilitado em seu ambiente, verifique se todas as cargas de trabalho principais estão funcionando conforme o esperado, como presença de IM &, chamadas P2P, Enterprise Voice etc.

**Validar se apenas o TLS 1.2 está sendo usado**

Faça com que sua equipe de segurança execute uma nova auditoria do tráfego do Skype for Business para garantir que os protocolos mais antigos TLS 1.0 e 1.1 não estão mais em uso.

Como alternativa, você pode usar o Internet Explorer para testar conexões TLS com serviços Web do Skype for Business Server 2015 após a desabilitação do TLS 1.0 e do TLS 1.1.

1. Iniciar o Internet Explorer.
2. Selecione **Ferramentas Opções** da  >  **Internet.**
3. Selecione a **guia** Avançado.
4. Em **Configurações,** role até a parte inferior.
5. Verifique se o TLS 1.0, o TLS 1.1 e o TLS 1.2 estão habilitados.
6. Procure a URL do Serviço Web Interno do seu pool do SfB 2015 (deve se conectar com êxito).
7. Volte para o Internet Explorer e desabilite a opção **Usar somente TLS 1.2.**
8. Navegue novamente pela URL do Serviço Web Interno do pool do SfB 2015 (deve não conseguir se conectar).

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Cenários de implantação avançada

Como alguns pré-requisitos de dependência são necessários para dar suporte ao TLS 1.2 no Skype for Business Server 2015, a instalação de mídia RTM falhará em qualquer sistema em que o TLS 1.0 e 1.1 tenham sido desabilitados.

**Implantação de novos servidores Standard Edition ou pools enterprise edition depois que o TLS 1.0 e 1.1 foram desabilitados em seu ambiente.**

**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Observe que estamos atualizando o SmartSetup para acomodar os binários SQL atualizados em uma atualização automática futura e atualizaremos este artigo no futuro.

**Opção 2:** Pré-instalar instâncias LOCAIS do SQL (RTCLOCAL e LYNCLOCAL)

1. Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64.exe) para a pasta local no FE. Digamos que o caminho da pasta <SQL_FOLDER_PATH>.
2. Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.
3. Crie a instância SQL RTCLOCAL executando o comando abaixo. Aguarde até SQLEXPR_x64.exe finalize antes de prosseguir:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. Crie a instância SQL LYNCLOCAL executando o comando abaixo. Aguarde até SQLEXPR_x64.exe finalize antes de prosseguir para a próxima etapa:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Execute a configuração do Skype for Business Server 2015 RTM.
2. Siga as etapas restantes da seção de pré-requisitos acima.

**Opção 3:** Você também pode substituir manualmente binários em um diretório de mídia de instalação local da seguinte maneira:

1. [Instalar pré-requisitos para o Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Instale o .NET 4.7: 
      - **Observação:** Apresentamos primeiro o suporte para o .NET 4.7 no Skype for Business Server 2015 CU5 (6.0.9319.281). Portanto, nas etapas posteriores abaixo, atualizaremos os Componentes Principais antes da instalação principal.
      - Baixe: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Referência: [Software que deve ser instalado antes de uma implantação do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copie arquivos/pastas ISO: 
    - Com o ISO do Skype for Business Server 2015 anexado, abra o diretório raiz da unidade em que ele está anexado como (Ex: D: \) no Explorador de Arquivos.
    - Copie todas as pastas e arquivos para uma pasta em um disco local (Ex: C:\SkypeForBusiness2015ISO).
    - **Observação:** Antes de instalar componentes, alguns arquivos precisarão ser atualizados para dar suporte ao TLS 1.2.
4. Substitua pacotes MSI/EXE: 
    - Substitua os pacotes MSI e EXE existentes na pasta /Setup/amd64/ da mídia de instalação no computador local.
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - Renomeie para SQLEXPR_x64 no computador local e substitua o arquivo existente na pasta Setup/amd64/ da mídia de instalação.
    - SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402 
        - **Observação:** Renomeie isso se necessário para sqlncli.msi e substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.
    - Objetos de gerenciamento SQL: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Observação:** O feature pack terá muitos itens que podem ser baixados. Selecione para baixar SharedManagementObjects.msi somente.
        - **Observação:** Substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.
    - Tipos do SQL CLR: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Observação:** O feature pack terá muitos itens que podem ser baixados. Selecione para baixar CQLSysClrTypes.msi somente
        - **Observação:** substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.
5. Instalar componentes principais: 
    - Execute Setup.exe da pasta Setup/amd64/ da mídia de instalação. Siga as instruções para instalar componentes principais
    - Feche os componentes principais.
6. Atualizar componentes principais: 
    - Baixe o Instalador de Atualização do Skype for Business.
    - Execute o instalador para atualizar os Componentes Principais e instalar os contadores de desempenho.
    - **Observação:** A partir do lançamento do CU6HF2, o recurso de atualização automática atualmente só será instalado até a CU6. Portanto, o atualizador deve ser executado separadamente para atualizar os Componentes Principais para 6.0.9319.516.
    - Referência: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Instalar Ferramentas Administrativas (Opcional): 
    - Isso instalará o Microsoft SQL Server 2012 Native Client, o SQL Server 2014 Management Objects (x64) e o Microsoft System CLR Types para SQL Server 2014 (x64) usando os arquivos atualizados. Além disso, o Construtor de Topologias e o Painel de Controle do Skype for Business Server 2015 estarão disponíveis no computador local.
8. Instalar o Armazenamento de Configuração Local (Etapa 1): 
     - Abra o Assistente de Implantação, clique em Instalar  ou Atualizar o Sistema do Skype for Business Server e clique em Executar na Etapa 1: Instalar o Armazenamento de Configuração Local.
     - Clique **em Próximo** na caixa de diálogo Instalar Armazenamento de **Configuração** Local.
     ![Caixa de diálogo Instalar Armazenamento de Configuração Local](../../media/local-configuration-store.png)
     - Revise os resultados e verifique se o Status da Tarefa foi Concluído. Revise o arquivo de log resultante clicando em **Exibir Log.**
     ![O status da tarefa aparece como Concluído](../../media/local-configuration-task-completed.png)
     - Clique em **Concluir**.
9. Configurar ou remover componentes do Skype for Business Server (Etapa 2):
    - Abra o Assistente de Implantação, clique em Instalar  ou Atualizar o **Sistema do Skype for Business Server** e clique em Executar na Etapa 2: Configurar ou Remover Componentes do Skype for Business Server
    - Clique **em Next** na caixa de diálogo Configurar Componentes do Skype for Business Server.
    ![a janela Configurar Componentes do Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Revise o log usando Exibir Log e valide se a instalação foi concluída sem problemas. 
    - Clique em **Concluir**.
10. Prossiga com a instalação e a configuração adicionais conforme necessário (você pode retomar os procedimentos de instalação normais neste ponto).
