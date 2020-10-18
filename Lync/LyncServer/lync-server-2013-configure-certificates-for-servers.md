---
title: 'Lync Server 2013: configurar certificados para servidores'
description: 'Lync Server 2013: configurar certificados para servidores.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fab2f55f25ed3a289dd2d51b080374b3844029c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578107"
---
# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configurar certificados para servidores no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-17_

Para concluir com êxito este procedimento, você deve estar conectado como usuário membro do grupo RTCUniversalServerAdmins ou ter as permissões corretas delegadas. Para obter detalhes sobre como delegar permissões, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Dependendo de sua organização e dos requisitos para a solicitação de certificados, podem ser necessárias outras associações de grupo. Consulte o grupo que gerencia a autoridade de certificação (CA) da PKI (infraestrutura de chave pública).

<div>


> [!NOTE]  
> O Lync Server 2013 inclui suporte para o pacote SHA-2 (SHA-2 usa comprimentos de Resumo de 224, 256, 384 ou 512 bits) do hash de resumo e dos algoritmos de assinatura para conexões de clientes que executam os sistemas operacionais Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Windows XP, além do Lync Phone Edition. Para dar suporte ao acesso externo usando o pacote SHA-2, o certificado externo é emitido por uma AC pública que também pode emitir um certificado com o mesmo comprimento de bit Digest.



</div>

<div>


> [!WARNING]  
> A seleção de qual o resumo de hash e o algoritmo de assinatura dependem dos clientes e dos servidores que usarão o certificado e outros computadores e dispositivos que os clientes e servidores irão se comunicar com quem também deve saber como usar os algoritmos usados no certificado. Para obter informações sobre quais tamanhos de resumo são suportados no sistema operacional e em alguns aplicativos cliente, consulte <A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A> .



</div>

Cada servidor Standard Edition ou servidor front-end requer até quatro certificados: o certificado oAuthTokenIssuer, um certificado padrão, um certificado interno da Web e um certificado externo da Web. No entanto, é possível solicitar e atribuir um único certificado padrão com entradas de nome alternativo de entidade apropriada, bem como o certificado oAuthTokenIssuer. Para obter detalhes sobre os requisitos de certificado, consulte [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Para obter detalhes sobre como solicitar, atribuir e instalar o certificado oAuthTokenIssuer, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Use o procedimento a seguir para solicitar, atribuir e instalar os certificados servidor Standard Edition ou servidor front-end. Repita o procedimento para cada servidor de front-end.

<div>


> [!IMPORTANT]  
> O procedimento a seguir descreve como configurar certificados de uma PKI corporativa interna implantada pela sua organização e com o processamento de solicitação offline. Para obter informações sobre como obter certificados de uma AC pública, consulte <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate Requirements for Internal Servers in Lync Server 2013</A> na documentação de planejamento. Além disso, este procedimento descreve como solicitar, atribuir e instalar certificados durante a configuração do servidor front-end. Se você solicitou certificados com antecedência, conforme descrito na seção <A href="lync-server-2013-request-certificates-in-advance-optional.md">solicitar certificados com antecedência (opcional) para Lync Server 2013</A> desta documentação de implantação ou não usar uma PKI corporativa interna implantada em sua organização para obter certificados, você deve modificar esse procedimento conforme apropriado.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Para configurar certificados para um servidor front-end

1.  No assistente de implantação do Lync Server, clique em **executar** ao lado de **etapa 3: solicitar, instalar ou atribuir certificados**.

2.  Na página **Assistente de Certificados**, clique em **Solicitar**.

3.  Na página **Solicitação de Certificado**, clique em **Avançar**.

4.  Na página **solicitações atrasadas ou imediatas** , você pode aceitar a opção padrão **enviar a solicitação imediatamente para uma autoridade de certificação online** clicando em **Avançar**. A autoridade de certificação interna com registro online automático deve estar disponível se você selecionar essa opção. Se você escolher a opção para atrasar a solicitação, você será solicitado a fornecer um nome e um local para salvar o arquivo de solicitação de certificado. A solicitação de certificado deve ser apresentada e processada por uma autoridade de certificação dentro da sua organização ou por uma autoridade de certificação pública. Você precisará importar a resposta do certificado e atribuí-la à função de certificado adequada.

5.  Na página **escolher uma autoridade de certificação (CA)** , selecione a opção **selecionar uma autoridade de certificação na lista detectada em seu ambiente** e, em seguida, selecione uma autoridade de certificação conhecida (através de registro no Active Directory Domain Services) na lista. Ou selecione a opção **especificar outra autoridade de certificação** , digite o nome de outra autoridade de certificação na caixa e clique em **Avançar**.

6.  Na página **Conta da Autoridade de Certificação**, são solicitadas credenciais para solicitar e processar a solicitação de certificado na AC. Você deve ter determinado se um nome de usuário e senha são necessários para solicitar um certificado antecipadamente. O administrador da sua AC terá a informação solicitada e pode ajudá-lo nesta etapa. Se for necessário fornecer credenciais alternativas, selecione a opção, forneça um nome de usuário e senha nas caixas de texto e clique em **Avançar**.

7.  Na página **Especificar Modelo de Certificado Alternativo**, para usar o modelo do Servidor Web padrão, clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se sua organização criou um modelo para uso como uma alternativa para o modelo padrão da AC do servidor Web, marque a caixa de seleção e insira o nome do modelo alternativo. Você precisará no nome de modelo conforme definido pelo administrador da AC.

    
    </div>

8.  Na página **Nome e Configurações de Segurança**, especifique um **Nome Amigável** que o permita identificar o certificado e o objetivo. Se deixá-lo em branco, um nome será gerado automaticamente. Defina o **Comprimento de bit** da chave ou aceite o padrão de 2048 bits. Selecione a **caixa de seleção marcar a chave privada do certificado como exportável** se você determinar que o certificado e a chave privada precisam ser movidos ou copiados para outros sistemas e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > O Lync Server 2013 tem requisitos mínimos para uma chave privada exportável. Um local está nos Servidores de Borda em um pool, onde o Serviço de Autenticação de Media Relay usa cópias do certificado, em vez dos certificados individuais para cada instância no pool.

    
    </div>

9.  Na página **informações da organização** , forneça, opcionalmente, as informações da organização e clique em **Avançar**.

10. Na página **informações geográficas** , forneça, opcionalmente, informações geográficas e clique em **Avançar**.

11. Na página **Nome da Entidade / Nomes Alternativos de Entidade**, veja os nomes alternativos de entidade que serão adicionados e clique em **Avançar**.

12. Na página **configuração do domínio SIP** , selecione o **domínio SIP**e clique em **Avançar**.

13. Na página **configurar nomes alternativos da entidade adicionais** , adicione quaisquer nomes alternativos de entidade adicionais necessários, incluindo qualquer um que possa ser necessário para domínios SIP adicionais no futuro e clique em **Avançar**.

14. Na página **Resumo da solicitação de certificado** , revise as informações no resumo. Se as informações estiverem corretas, clique em **Avançar**. Se você precisar corrigir ou modificar uma configuração, clique em **voltar** à página adequada para fazer a correção ou modificação.

15. Na página **Executando Comandos**, clique em **Avançar**.

16. Na página **status da solicitação de certificado online** , revise as informações retornadas. Você deve observar que o certificado foi emitido e instalado no repositório de certificados local. Se ele for relatado como tendo sido emitido e instalado, mas não for válido, verifique se o certificado raiz da autoridade de certificação foi instalado no repositório da autoridade de certificação raiz confiável do servidor. Consulte a documentação da autoridade de certificação sobre como recuperar um certificado de autoridade de certificação raiz confiável. Se você precisar exibir o certificado recuperado, clique em **Exibir detalhes do certificado**. Por padrão, a caixa de seleção para **atribuir o certificado aos usos de certificado do Lync Server** é verificada. Se você deseja atribuir manualmente o certificado, desmarque a caixa de seleção e clique em **concluir**.

17. Se você desmarcou a caixa de seleção para **atribuir o certificado aos usos de certificado do Lync Server** na página anterior, será exibida a página **atribuição de certificado** . Clique em **Avançar**.

18. Na página **repositório de certificados** , selecione o certificado que você solicitou. Se quiser exibir o certificado, clique em **Exibir detalhes do certificado**e clique em **Avançar** para continuar.
    
    <div>
    

    > [!NOTE]  
    > Se a página <STRONG>status da solicitação de certificado online</STRONG> relatou um problema com o certificado, como o certificado não é válido, a exibição do certificado real pode ajudar a resolver o problema. Dois problemas específicos que podem fazer com que um certificado não seja válido é o certificado de autoridade de certificação raiz confiável ausente mencionado anteriormente e uma chave privada ausente associada ao certificado. Consulte a documentação da autoridade de certificação para resolver esses dois problemas.

    
    </div>

19. Na página **Resumo de atribuição de certificado** , revise as informações apresentadas para certificar-se de que esse é o certificado que deve ser atribuído e clique em **Avançar**.

20. Na página **executando comandos** , revise a saída do comando. Clique em **Exibir log** se quiser revisar o processo de atribuição ou se houve um erro ou aviso emitido. Após concluir a revisão, clique em **concluir**.

21. Na página **Assistente de certificado** , verifique se o **status** do certificado é "atribuído" e clique em **Fechar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de infraestrutura de certificado para o Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

