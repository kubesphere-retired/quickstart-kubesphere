Ref 函数可指代那些在创建堆栈时指定的输入参数。
您可以使用 Ref 函数引用资源的标识属性。通常，这是资源的实体名称；然而，有时，它也可以作为一个标识符，例如，AWS::EC2::EIP 资源的 IP 地址或 Amazon SNS 主题的 Amazon 资源名称 (ARN)。有关 Ref 函数返回的一系列值的信息，请参阅 Ref 函数。以下模板包含一个 AWS::EC2::Instance 资源。该资源的 SecurityGroups 属性调用了 Ref 函数，以便能参阅 AWS::EC2::SecurityGroup 资源，即 InstanceSecurityGroup。

若要获得这些属性，您可以使用Fn::GetAtt函数。以下模板创建了一个 CloudFront 分配资源，通过使用 Fn::GetAtt 函数，该资源指定了 S3 存储桶资源的 DNS 名，以便能获得 S3 存储桶的 DomainName 属性。
FN::GetAtt 函数有两个参数，即资源的逻辑名和要检索的属性名。有关这些资源的可用属性的完整列表，请参阅Fn::GetAtt。您将发现 Fn::GetAtt 函数在一个数组中列出其两个参数。对于采用多个参数的函数，可以使用数组来指定其参数。
Fn::GetAtt 内部函数返回模板中的资源的属性值。有关特定资源的 GetAtt 返回值的更多信息，请参阅 资源和属性参考 中该资源的文档。

内部函数 Fn::Sub 将输入字符串中的变量替换为您指定的值。在您的模板中，可以使用此函数构建命令或输出，其中包含在创建或更新堆栈之前不可用的值。