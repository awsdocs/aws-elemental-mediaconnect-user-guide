# Reservations for AWS Elemental MediaConnect<a name="reservations"></a>

Reservations provide you with significant savings on your AWS Elemental MediaConnect costs compared to on\-demand pricing\. 

A *reservation* is a commitment to use a specific amount of outbound bandwidth each month over the course of a specified duration\. In return, you pay a discounted hourly rate for that bandwidth\. The reservation is allocated and billed on a monthly basis through the duration of the reservation\.

The discounted rate applies to outbound bandwidth from all of the MediaConnect flows in your account up to the amount of bandwidth specified in the reservation\. 

*Outbound bandwidth* refers to data that is transferred from a MediaConnect flow to a location or endpoint outside of the AWS Cloud\. It does not include data transferred *in* to your MediaConnect flow, nor does it include data transferred from a MediaConnect flow to any location within the AWS Cloud\.

For information on charges for reservations, see the [MediaConnect price list](https://aws.amazon.com/mediaconnect/pricing/)\.

## How billing works<a name="reservations-unused-minutes"></a>

Reserved outbound bandwidth is billed hourly\. For each billing cycle, AWS charges your account for outbound bandwidth at the discounted rate, as specified in your reservation\. If your account uses more outbound bandwidth than is covered in the reservation, the overage is charged at on\-demand rates\. If your account used less bandwidth, AWS charges you for the amount of outbound bandwidth that's specified in the reservation\. Unused bandwidth is not carried over to the next month\.