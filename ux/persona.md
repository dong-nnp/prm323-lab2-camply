
# Persona 1 - Sinh viên năng động

## Tên giả định & Archetype:

**Nguyễn Minh Anh — Sinh viên thích khám phá trải nghiệm mới.**

- 20 tuổi, sinh viên đại học năm 2.
- Quan tâm workshop, âm nhạc, giao lưu và hoạt động câu lạc bộ.
- Thường muốn biết trường đang có gì thú vị trước khi xác định sự kiện cụ thể để tham gia.

## Ưu tiên & lý do:

- **Primary.**
- **Lí do**: Nhu cầu đại diện trực tiếp cho bài toán cốt lõi mà Camply giải quyết, chính là giúp sinh viên khám phá các sự kiện trong trường ngay cả khi họ chưa biết chính xác mình muốn tham gia sự kiện nào.

## Usage context:

- **Thời điểm:** Nghỉ giữa các tiết, nghỉ trưa hoặc lúc chờ xe; muốn xem nhanh rồi quay lại việc học hoặc việc đang làm.
- **Thiết bị:** Smartphone, màn hình dọc; đôi lúc chỉ rảnh một tay. Đáp ứng cho 2 hệ điều hành phổ biến hiện nay Android và iOS.
- **Môi trường:** Trong khuôn viên trường, lớp học lúc nghỉ, khu tự học hoặc nơi chờ; có thể gặp ánh sáng mạnh và kết nối không ổn định.
- **Sự chú ý:** Dễ bị ngắt bởi tin nhắn, bạn bè hoặc giờ vào lớp. Một phiên xem khoảng 1–5 phút là giả định cần xác minh.

## Goals:

1. Giúp sinh viên nhanh chóng khám phá và tìm được một hoạt động trong trường phù hợp với sở thích, ngay cả khi họ chưa biết tên sự kiện hoặc đơn vị tổ chức.

2. Giúp sinh viên nhanh chóng hiểu sự kiện gồm những gì, diễn ra khi nào, ở đâu và còn khả năng đăng ký hay không, từ đó xác định hoạt động nào phù hợp và thực tế có thể tham gia.

3. Giúp sinh viên biết mình đã đăng ký gì và tìm lại đúng lịch, địa điểm, trạng thái trước khi đến sự kiện.

## Job to Be Done:

Khi có thời gian rảnh và muốn thử một hoạt động mới trong trường, tôi muốn biết các sự kiện phù hợp, hiểu điều kiện tham gia và xác nhận việc đăng ký, để chủ động có thêm trải nghiệm mà không bỏ lỡ vì thiếu thông tin.

## Current behaviors & workaround:

- Lướt fanpage trường/CLB, nhóm sinh viên và bài chia sẻ của bạn bè; thường biết đến sự kiện trong lúc xem nội dung khác.
- Cuộn xem hình và tên để nhận diện chủ đề; tìm ngày giờ, địa điểm và tình trạng đăng ký trước khi đọc mô tả dài.
- Mở đường dẫn/form từ bài đăng để đăng ký; kiểm tra phản hồi hoặc tin nhắn xác nhận nếu có.
- Chụp màn hình, lưu bài hoặc gửi đường dẫn vào tin nhắn để tra lại; phải xem nhiều nguồn khi quên lịch hay trạng thái đăng ký.
- Giả định dùng điện thoại qua nhiều phiên ngắn, đôi lúc thao tác một tay. Tần suất tìm/đăng ký sự kiện và mức độ quen các kiểu điều hướng chưa được xác minh.

## Pain points:

1. **Thông tin phân tán:** Khi muốn tìm hoạt động mới, phải kiểm tra nhiều kênh → mất thời gian và có thể biết đến sự kiện khi đã hết hạn đăng ký.

2. **Thông tin quyết định khó tìm:** Ngày giờ, địa điểm và điều kiện đăng ký lẫn trong bài viết dài → phải đọc lại, khó so sánh và dễ bỏ sót thông tin quan trọng.

3. **Khó tra lại sau đăng ký:** Bài đăng, form và xác nhận nằm rải rác → không chắc đã đăng ký gì, phải tìm lại lịch/địa điểm trước khi tham gia.

## Motivations:

- **Trải nghiệm mới:** Muốn thử những hoạt động ngoài việc học và tận dụng đời sống đại học.
  - **UX implication:** Giao diện nên hỗ trợ hành vi khám phá thay vì chỉ tìm kiếm theo tên. Home cần có nội dung để duyệt ngay như `Hôm nay`, `Tuần này`, `Workshop`, `Âm nhạc` hoặc `Đề xuất cho bạn`. Event Card nên có hình ảnh và tiêu đề nổi bật để người dùng dễ bị thu hút bởi những hoạt động mới.

- **Chủ động lựa chọn:** Muốn tự khám phá và quyết định theo sở thích, không phụ thuộc hoàn toàn vào lời giới thiệu.
  - **UX implication:** Người dùng cần có quyền kiểm soát trong quá trình tìm kiếm và lựa chọn. Search và Filter phải dễ tiếp cận, category rõ ràng, và Event Detail phải cung cấp đủ thông tin như nội dung, thời gian, địa điểm, đơn vị tổ chức và trạng thái đăng ký để người dùng tự đánh giá thay vì phải tìm thêm ở nguồn khác.

- **Yên tâm tham gia:** Coi trọng thông tin rõ ràng và phản hồi đáng tin để biết đăng ký đã được ghi nhận.
  - **UX implication:** Sau khi đăng ký, hệ thống cần phản hồi ngay bằng thông báo rõ ràng như `Đăng ký thành công` và cập nhật trạng thái sự kiện thành `Đã đăng ký`. Trạng thái này phải nhất quán giữa Event Detail và `My Events`, để người dùng có thể kiểm tra lại mà không nghi ngờ việc đăng ký đã được lưu hay chưa.

## Constraints:

- **Kỹ năng:** Mức thành thạo tìm kiếm, bộ lọc và điều hướng chưa biết; cần nhãn hành động dễ hiểu, tránh yêu cầu ghi nhớ thao tác ẩn.
- **Thiết bị:** Màn hình nhỏ, có thể chỉ dùng một tay; kết nối có thể chập chờn, cần nhận biết lỗi tải và biết cách thử lại.
- **Thời gian:** Khoảng rảnh ngắn, dễ bị gián đoạn; khó đọc nhiều nội dung trước khi thấy thông tin chính.
- **Accessibility:** Nhu cầu cá nhân về thị giác, vận động và công nghệ hỗ trợ chưa được khảo sát. Nhu cầu theo tình huống giả định gồm đọc ngoài trời và chạm bằng một tay; cần chữ dễ đọc, vùng chạm đủ lớn, trạng thái có nhãn chữ và khả năng phóng to nội dung.
- **Quyền hạn:** Là người tham gia; không có tác vụ quản trị hoặc chỉnh sửa thông tin sự kiện trong hồ sơ này.

## Critical scenarios:

1. **Khám phá và đăng ký:** Giữa hai tiết học, Minh Anh muốn tìm một hoạt động thú vị trong tuần nhưng chưa biết tên sự kiện. Mở Camply, duyệt danh sách, xem chi tiết, đối chiếu lịch/địa điểm rồi đăng ký. Kết quả mong muốn là chọn được hoạt động phù hợp và thấy đăng ký của mình trong My Events.

2. **Tra lại và hoàn tác:** Trước khi tham gia, Minh Anh mở My Events để kiểm tra địa điểm; trong lúc thao tác, vô tình hủy đăng ký. Muốn nhận biết việc vừa xảy ra và dùng Undo để khôi phục. Kết quả mong muốn là đọc đúng lịch/địa điểm và xác nhận trạng thái đã đăng ký được khôi phục ở cả My Events lẫn chi tiết. Khả năng phục hồi suất sau khi hủy cần được xác định theo chính sách hệ thống.

## Success criteria:

Các mục tiêu đề xuất dưới đây dùng cho prototype có tài khoản đã đăng nhập và dữ liệu sự kiện phù hợp; chưa có kết quả kiểm thử.

- **Khám phá:** Trong ≤30 giây từ lúc mở Camply, mở chi tiết một sự kiện phù hợp và giải thích đúng lý do chọn.
- **Đăng ký:** Trong ≤120 giây tổng cộng từ cùng điểm bắt đầu, hoàn thành đăng ký, tìm thấy sự kiện trong My Events và nêu đúng thời gian, địa điểm, trạng thái.
- **Tra lại:** Trong ≤20 giây từ Home, tìm đúng sự kiện đã đăng ký được yêu cầu và đọc đúng lịch/địa điểm.
- **Hoàn tác:** Tự nhận biết đã hủy nhầm, tìm và dùng Undo trong cơ hội phục hồi đang hiển thị nếu hệ thống hỗ trợ; xác nhận đúng trạng thái sau khôi phục. Thời lượng hiển thị Undo và khả năng phục hồi suất cần được kiểm chứng.

Ghi thời gian, lỗi thao tác và mức trợ giúp; tác vụ thành công khi người dùng hoàn tất và hiểu đúng kết quả mà không cần gợi ý.

## Research evidence

Thông tin trong persona được xây dựng từ quá trình **research hiện trạng chung về cách sinh viên tìm kiếm, tiếp cận, đăng ký và theo dõi các sự kiện trong môi trường đại học**.

Các nội dung như hành vi hiện tại, pain points, motivations, constraints và nhu cầu được tổng hợp từ những patterns phổ biến được giả định trong bối cảnh sử dụng các kênh như fanpage trường, fanpage câu lạc bộ, nhóm sinh viên, bài chia sẻ trên mạng xã hội và các form đăng ký sự kiện.

Hiện chưa thực hiện phỏng vấn hoặc quan sát trực tiếp một nhóm người dùng cụ thể, vì vậy persona này vẫn được xem là **research-based proto-persona**. Các giả định về tần suất sử dụng, thời lượng phiên, mức độ thành thạo, hành vi cụ thể và nhu cầu accessibility vẫn cần được kiểm chứng thêm bằng usability test hoặc nghiên cứu người dùng thực tế.

## Evidence status:

**Proto-Persona — chưa xác thực.**

- **Assumed:** Tuổi cụ thể, năm học, hành vi, workaround, thời lượng phiên, bối cảnh thiết bị, động lực bổ sung, rào cản và scenarios. Các mô tả người dùng đang là giả định cần kiểm chứng.
- **Inferred:** Lập luận về ưu tiên thông tin và các phương án UI được suy ra từ nhu cầu giả định.
- **Observed / Reported:** Chưa có dữ liệu từ quan sát hoặc lời thuật lại của người tham gia nghiên cứu thực tế.

## Open questions:

- Lần gần nhất tìm sự kiện, sinh viên đã biết tên trước hay bắt đầu bằng việc khám phá? Đã tìm ở đâu và làm những bước nào?
- Thông tin nào quyết định việc tham gia? Trở ngại cụ thể nằm ở bước tìm, cân nhắc, đăng ký hay tra lại?
- Hiện xác nhận và tra lại đăng ký như thế nào? Có từng bỏ lỡ hoặc nhầm lịch vì thông tin thiếu/rải rác không?
- Thiết bị, tần suất và thời lượng sử dụng thực tế là gì? Có nhu cầu phóng to chữ, trình đọc màn hình hoặc hỗ trợ thao tác nào?

## Potential UI Decisions to Test

| Nhu cầu của người dùng | Giả thuyết thiết kế UI | Cách kiểm chứng |
| :-- | :-- | :-- |
| **Khám phá sự kiện khi chưa biết tên cụ thể** | Màn hình Home cần hiển thị ngay các sự kiện để người dùng có thể lướt và khám phá mà không bắt buộc phải nhập từ khóa. Các sự kiện nên được phân nhóm theo thời gian hoặc chủ đề như `Hôm nay`, `Tuần này`, `Workshop`, `Âm nhạc`. Thanh Search vẫn cần dễ nhìn thấy để sử dụng khi người dùng đã biết mình muốn tìm gì. | Giao cho người dùng nhiệm vụ: **“Hãy tìm một sự kiện trong tuần này mà bạn cảm thấy muốn tham gia.”** Không cung cấp tên sự kiện cụ thể. Quan sát người dùng bắt đầu từ đâu, họ có hiểu cách duyệt các nhóm sự kiện hay không, mất bao lâu để chọn được một sự kiện và lý do gì khiến họ chọn sự kiện đó. |
| **Hiểu đủ thông tin trước khi quyết định tham gia** | Event Card cần giúp người dùng nhận diện nhanh sự kiện. Khi mở Event Detail, các thông tin quan trọng như **tên sự kiện, nội dung chính, ngày giờ, địa điểm và trạng thái đăng ký** phải dễ nhìn thấy trước các thông tin phụ hoặc phần mô tả dài. | Giao cho người dùng nhiệm vụ: **“Hãy xem sự kiện này và quyết định xem bạn có muốn tham gia hay không.”** Sau đó hỏi người dùng: sự kiện nói về điều gì, diễn ra khi nào, ở đâu và hiện còn đăng ký được hay không. Quan sát người dùng có phải cuộn nhiều, quay lại màn hình trước hoặc mất nhiều thời gian để tìm các thông tin này hay không. |
| **Biết chắc mình đã đăng ký thành công** | Nút đăng ký phải có nhãn rõ như `Đăng ký`. Sau khi người dùng đăng ký, giao diện cần hiển thị phản hồi rõ ràng như `Đăng ký thành công` và trạng thái của sự kiện phải chuyển sang `Đã đăng ký`. | Yêu cầu người dùng đăng ký một sự kiện. Sau khi hoàn tất, hỏi: **“Theo bạn, bạn đã đăng ký thành công chưa? Điều gì trên giao diện khiến bạn biết điều đó?”** Quan sát xem người dùng có nhận ra thông báo thành công và trạng thái `Đã đăng ký` hay không, hay vẫn cảm thấy chưa chắc chắn và muốn nhấn nút đăng ký thêm lần nữa. |
| **Tìm lại nhanh sự kiện đã đăng ký** | Ứng dụng cần có mục `My Events` dễ truy cập để người dùng xem lại những sự kiện mình đã đăng ký. Trạng thái của sự kiện trong `My Events` phải giống với trạng thái hiển thị trên Event Detail để tránh gây nhầm lẫn. | Sau khi người dùng đăng ký một sự kiện, yêu cầu họ rời khỏi màn hình hiện tại rồi thực hiện nhiệm vụ: **“Hãy tìm lại sự kiện mà bạn vừa đăng ký.”** Đo số thao tác và thời gian cần để tìm lại. Quan sát xem người dùng có biết nên vào đâu và có hiểu đúng trạng thái đăng ký hay không. |
| **Có thể phục hồi khi hủy đăng ký nhầm** | Sau khi hủy đăng ký, giao diện nên hiển thị thông báo rõ ràng. Có thể thử nghiệm `Hoàn tác` (`Undo`) nếu chính sách và cơ chế giữ suất cho phép; không được tự chuyển thành `Đã đăng ký` khi suất đã được phân bổ cho người khác. | Tạo tình huống người dùng định hủy nhầm và kiểm tra khả năng ngăn thao tác qua dialog xác nhận. Nếu prototype hỗ trợ Undo, yêu cầu thử khôi phục và quan sát người dùng hiểu đúng kết quả hay không. |
| **Sử dụng nhanh trên điện thoại, đôi khi chỉ bằng một tay** | Các hành động chính như điều hướng, mở sự kiện, đăng ký và truy cập `My Events` cần nằm ở vị trí dễ chạm. Nút và vùng tương tác phải đủ lớn để giảm thao tác nhầm. Nội dung chính cần có thứ bậc rõ để người dùng không phải đọc quá nhiều. | Cho người dùng thực hiện các tác vụ chính trên màn hình mobile, đặc biệt ở kích thước 360 dp. Quan sát xem họ có bấm nhầm, phải đổi tay, khó với tới nút, bỏ sót hành động chính hoặc phải cuộn quá nhiều trước khi tìm thấy thông tin cần thiết hay không. |
| **Biết phải làm gì khi nội dung tải lỗi** | Nếu danh sách sự kiện không tải được, giao diện phải hiển thị thông báo dễ hiểu về việc tải thất bại và cung cấp nút `Thử lại`. Không nên để màn hình trắng hoặc chỉ hiển thị mã lỗi kỹ thuật. | Mô phỏng tình huống danh sách sự kiện tải thất bại. Hỏi người dùng: **“Theo bạn, chuyện gì vừa xảy ra và bạn sẽ làm gì tiếp theo?”** Quan sát xem họ có hiểu lỗi, có nhận ra nút `Thử lại` và có thể tiếp tục sử dụng ứng dụng mà không phải thoát rồi mở lại hay không. |

---

# Persona 2 – Ban tổ chức sự kiện (Club Organizer)

## Tên giả định & Archetype

**Phạm Minh Quân — Sinh viên phụ trách tổ chức và vận hành sự kiện câu lạc bộ.**

- 21 tuổi, sinh viên đại học năm 3.
- Là thành viên ban tổ chức của một câu lạc bộ trong trường, tham gia chuẩn bị workshop, hoạt động giao lưu và các sự kiện dành cho sinh viên.
- Được phân công quản lý nội dung công bố, thông tin đăng ký, những thay đổi của sự kiện và hoạt động check-in.
- Muốn tổ chức sự kiện có quy trình rõ ràng, giảm sai sót khi xử lý thông tin và biết chính xác tình hình người tham gia.

## Ưu tiên & lý do

- **Secondary.**
- **Lý do:** Mục tiêu trọng tâm của Camply là giúp sinh viên khám phá và tham gia sự kiện, nên nhóm Student được ưu tiên trong định hướng trải nghiệm chính. Tuy nhiên, Club Organizer là actor thiết yếu ở phía cung cấp và vận hành sự kiện: tạo nội dung, thiết lập chính sách tham gia, xử lý thay đổi và xác minh người đến thực tế.

Persona này bổ sung góc nhìn của người tổ chức để bảo đảm những gì Student nhìn thấy và sử dụng trong Camply là thông tin chính xác, cập nhật và có thể vận hành được. **Secondary là mức độ ưu tiên của persona trong bộ persona tổng thể, không có nghĩa F04–F06 là các nghiệp vụ không quan trọng.**

## Usage context

- **Thời điểm:** Trước sự kiện khi chuẩn bị và công bố; trong thời gian mở đăng ký khi theo dõi danh sách; sát ngày diễn ra khi chỉnh sửa hoặc xử lý phát sinh; tại cổng khi tiếp đón và check-in.
- **Thiết bị:** Giả định sử dụng laptop để nhập nhiều thông tin và smartphone để xem nhanh, quét QR tại địa điểm tổ chức. Thiết bị thực tế và việc Camply hỗ trợ từng tác vụ trên mỗi thiết bị cần được xác minh.
- **Môi trường:** Phòng sinh hoạt CLB, khuôn viên trường, nơi chuẩn bị hậu cần và khu vực check-in đông người; kết nối mạng có thể không ổn định.
- **Sự chú ý:** Phải phối hợp với nhiều thành viên, dễ bị gián đoạn bởi tin nhắn, công việc hậu cần hoặc tình huống phát sinh.
- **Bối cảnh quyết định:** Trước khi Publish cần ưu tiên sự đầy đủ và chính xác; khi sự kiện đang diễn ra cần phản hồi nhanh nhưng tuyệt đối không ghi nhận check-in sai.

## Goals

1. Tạo và công bố sự kiện với thông tin đầy đủ, chính xác về nội dung, thời gian, địa điểm và đơn vị tổ chức.

2. Thiết lập rõ **audience**, **eligibility**, hình thức tham gia, sức chứa, thời hạn đăng ký và waitlist (nếu áp dụng) để người tham gia hiểu đúng điều kiện.

3. Theo dõi số người đã đăng ký, đang chờ và xác nhận dự định tham dự để chuẩn bị nguồn lực phù hợp, không nhầm các trạng thái này với số người thực tế đến.

4. Chỉnh sửa hoặc hủy sự kiện an toàn khi có thay đổi, bảo đảm người bị ảnh hưởng được thông báo và trạng thái vé nhất quán.

5. Kiểm tra vé QR, phát hiện vé trùng hoặc không hợp lệ, ghi nhận check-in chính xác.

6. Xem số người đã check-in thực tế để đối chiếu với số đăng ký và đánh giá kết quả tổ chức.

## Job to Be Done

Khi được giao phụ trách một sự kiện của câu lạc bộ, tôi muốn tạo và công bố thông tin chính xác, quản lý trạng thái đăng ký, cập nhật thay đổi và kiểm tra vé tại cổng trong một quy trình thống nhất, để giảm thao tác thủ công, tránh nhầm lẫn cho sinh viên và nắm được số người thực sự tham gia.

## Current behaviors & workaround

- Có thể chuẩn bị tên, mô tả, hình ảnh, lịch trình và thông tin địa điểm rồi đăng thông báo trên fanpage CLB hoặc các nhóm sinh viên.
- Có thể dùng biểu mẫu trực tuyến để thu thập đăng ký và bảng tính để theo dõi người tham gia.
- Kiểm tra số người đăng ký, đối chiếu danh sách và tình trạng còn chỗ theo cách thủ công hoặc qua nhiều công cụ.
- Khi thay đổi thời gian, địa điểm hoặc phải hủy sự kiện, có thể sửa bài đăng cũ và gửi thông báo bổ sung qua các kênh khác nhau.
- Trước ngày diễn ra, có thể chuẩn bị danh sách đăng ký để nhân sự tại cổng đối chiếu.
- Trong ngày tổ chức, có thể kiểm tra tên, mã đăng ký hoặc vé của sinh viên rồi đánh dấu đã đến.
- Sau sự kiện, có thể tổng hợp lại số lượt đăng ký và số người thực sự tham gia từ danh sách check-in.
- **Workaround giả định:** Kết hợp fanpage, biểu mẫu, bảng tính và tin nhắn để xử lý những phần việc chưa được tập trung trong một hệ thống.

Các hành vi và công cụ trên là giả thuyết dựa trên bối cảnh nghiệp vụ; chưa có quan sát hoặc phỏng vấn ban tổ chức để xác nhận mức độ phổ biến.

## Pain points

1. **Thông tin sự kiện thiếu thống nhất:** Bài giới thiệu, form và tin nhắn cập nhật có thể khác nhau → sinh viên hiểu sai giờ, địa điểm hoặc điều kiện tham gia, ban tổ chức phải giải thích nhiều lần.

2. **Khó kiểm soát số lượng và trạng thái:** Dữ liệu đăng ký và danh sách chờ có thể nằm ở nhiều nguồn → khó biết chính xác số người đã đăng ký, đang chờ hoặc xác nhận sẽ đến.

3. **Dễ nhập thiếu hoặc sai khi công bố:** Các trường như điều kiện tham gia, sức chứa, thời hạn đăng ký hoặc hình thức tham gia dễ bị bỏ sót → phải chỉnh sửa sau khi đã có người xem hoặc đăng ký.

4. **Thay đổi sau công bố dễ gây nhầm lẫn:** Đổi giờ, đổi địa điểm hoặc hủy sự kiện ảnh hưởng đến người đã đăng ký → khó bảo đảm mọi người đều nhận và sử dụng thông tin mới.

5. **Check-in có nguy cơ chậm hoặc ghi nhận trùng:** Khi nhiều sinh viên đến cùng lúc, việc đối chiếu thủ công dễ gây ùn tắc hoặc chấp nhận nhầm vé không hợp lệ.

6. **Số đăng ký không phản ánh số tham dự thực tế:** Người đăng ký có thể không đến → nếu thiếu dữ liệu check-in đáng tin cậy thì khó tổng hợp kết quả tổ chức.

## Motivations

- **Tổ chức chuyên nghiệp:** Muốn thông tin sự kiện rõ ràng, nhất quán và tạo sự tin tưởng cho sinh viên.
  - **UX implication:** Luồng Create Event nên nhóm trường theo thông tin cơ bản, lịch/địa điểm và chính sách tham gia; có validation, `Save Draft` và `Review Event` trước `Publish`.

- **Chủ động kiểm soát:** Muốn theo dõi nhu cầu tham gia để chuẩn bị số chỗ và nhân sự phù hợp.
  - **UX implication:** Organizer Dashboard/Event Management cần phân biệt `Registered`, `Waitlisted` và `Planning to Attend`; làm rõ các chỉ số này không đồng nghĩa `Checked-in`.

- **Giảm rủi ro khi xử lý thay đổi:** Muốn tránh gửi thông tin sai hoặc vô tình hủy một sự kiện đã có người đăng ký.
  - **UX implication:** Edit/Cancel cần cho xem lại nội dung và tác động, có bước xác nhận đối với thao tác nhạy cảm và phản hồi rõ trạng thái sau khi lưu. Thay đổi quan trọng cần thông báo cho người bị ảnh hưởng.

- **Vận hành nhanh và chính xác:** Muốn kiểm tra vé kịp thời khi nhiều sinh viên đến, đồng thời không để một vé được ghi nhận hai lần.
  - **UX implication:** QR Scanner cần phản hồi rõ `Valid`, `Duplicate`, `Invalid` và lỗi kết nối; chỉ ghi nhận `Checked-in` khi xác minh thành công.

## Constraints

- **Thời gian:** Trước sự kiện cần xử lý nhiều đầu việc; trong ngày diễn ra cần thao tác nhanh, ít bước và dễ nhận diện kết quả.
- **Sự chú ý:** Dễ bị gián đoạn bởi công việc hậu cần và yêu cầu từ thành viên khác; UI phải giúp xác định đang quản lý sự kiện nào, đang ở bước nào.
- **Thiết bị:** Giả định có thể dùng laptop và smartphone trong những bối cảnh khác nhau; không nên mặc định một tác vụ phức tạp sẽ luôn được thực hiện trên màn hình lớn.
- **Kết nối:** Có thể mất mạng tại nơi check-in; không được báo thành công hoặc cộng số check-in khi hệ thống chưa xác minh được vé.
- **Kỹ năng:** Mức độ quen dùng công cụ quản lý sự kiện khác nhau; các nhãn như `Audience`, `Eligibility`, `Registration Required` và `Waitlisted` cần được diễn giải dễ hiểu.
- **Accessibility:** Chưa có dữ liệu về nhu cầu cá nhân. Giao diện cần vùng chạm đủ lớn, chữ dễ đọc, trạng thái có nhãn chữ thay vì chỉ thể hiện bằng màu.
- **Quyền hạn:** Chỉ quản lý những sự kiện được phân quyền; tài liệu chưa xác định chi tiết vai trò và phân quyền giữa các thành viên trong cùng ban tổ chức.

## Critical scenarios

1. **Tạo và công bố sự kiện (F04):** Minh Quân được giao đăng workshop của CLB. Anh vào Organizer Dashboard, chọn `Create Event`, nhập thông tin cơ bản, thời gian, địa điểm, audience, eligibility, registration policy, capacity và thời hạn đăng ký. Trước khi Publish, anh muốn kiểm tra lại những thông tin quan trọng. **Kết quả mong muốn:** Sự kiện được công bố khi dữ liệu hợp lệ; nếu chưa xong có thể `Save Draft`; trường không hợp lệ được chỉ rõ để sửa.

2. **Cập nhật hoặc hủy sự kiện (F05):** Workshop đã có sinh viên đăng ký nhưng phải đổi phòng hoặc đổi giờ. Minh Quân chọn sự kiện đã đăng, thực hiện `Edit`, xem lại thay đổi và xác nhận. Nếu buộc phải `Cancel`, anh cần thấy cảnh báo về hậu quả trước khi quyết định. **Kết quả mong muốn:** Thay đổi được lưu và người bị ảnh hưởng được thông báo; khi hủy, vé không còn hiệu lực; nếu xử lý thất bại, hệ thống giữ trạng thái cũ và hiển thị lỗi.

3. **Quản lý danh sách và check-in (F06):** Vào ngày diễn ra, Minh Quân kiểm tra số lượng `Registered`, `Waitlisted`, `Planning to Attend`, sau đó mở QR Scanner để tiếp nhận sinh viên tại cổng. Anh lần lượt gặp vé hợp lệ, vé đã check-in và vé sai sự kiện. **Kết quả mong muốn:** Vé hợp lệ được ghi nhận đúng một lần; vé trùng và vé không hợp lệ bị từ chối; `Checked-in` phản ánh số lượt xác minh thành công, kể cả khi mạng không ổn định.

## Success criteria

Các mục tiêu dưới đây là ngưỡng đề xuất để kiểm thử prototype với tài khoản Organizer đã đăng nhập và bộ dữ liệu được cung cấp sẵn; chưa phải kết quả usability test.

- **Tạo sự kiện:** Trong ≤8 phút, tạo và Publish một sự kiện từ dữ liệu đã chuẩn bị, chọn đúng hình thức tham gia và không bỏ sót trường bắt buộc.
- **Hiểu lỗi form:** Nhận biết đúng trường sai hoặc thiếu và sửa được mà không cần hướng dẫn.
- **Phân biệt trạng thái:** Xác định đúng ý nghĩa và số lượng của `Registered`, `Waitlisted`, `Planning to Attend`, `Checked-in` từ màn hình được cung cấp.
- **Chỉnh sửa:** Trong ≤2 phút, tìm đúng sự kiện, thay đổi một thông tin được chỉ định và nhận biết kết quả cập nhật.
- **Hủy an toàn:** Nhận biết hậu quả của `Cancel` và có thể dừng thao tác trước bước xác nhận khi không muốn hủy.
- **Check-in:** Trong điều kiện kiểm thử có phản hồi xác minh, xử lý một lượt quét trong ≤10 giây và phân loại chính xác `Valid`, `Duplicate`, `Invalid`.
- **Lỗi kết nối:** Khi quét thất bại do mất mạng, nhận biết vé chưa được xác minh và không nhầm đó là check-in thành công.

Ghi thời gian, số thao tác, số lỗi và mức trợ giúp. Tác vụ thành công khi người dùng hoàn tất nghiệp vụ và giải thích đúng trạng thái mà không cần gợi ý.

## Research evidence

Persona được xây dựng dựa trên **đặc tả 6 User Flow của Camply**, tập trung vào F04 – Create & Publish Event, F05 – Manage Event Changes & Cancellation và F06 – Manage Attendees & Event Check-in.

Tài liệu mô tả ba nhóm vấn đề nghiệp vụ: thông tin và chính sách sự kiện có thể thiếu thống nhất; thay đổi sau công bố có thể ảnh hưởng đến người đã đăng ký; việc kiểm tra vé thủ công có nguy cơ ghi nhận nhầm hoặc trùng. Đây là **các giả thuyết thiết kế trong tài liệu**, chưa phải phát hiện đã được xác nhận từ nghiên cứu người dùng.

Các mô tả về cách ban tổ chức hiện dùng fanpage, form, bảng tính, phân công nhân sự hoặc sử dụng thiết bị là giả định bổ sung để hình thành persona; cần kiểm chứng bằng phỏng vấn, quan sát quy trình thực tế và usability test.

## Evidence status

**Proto-Persona — chưa xác thực.**

- **Provided:** Actor Club Organizer; các nhiệm vụ tạo/công bố, chỉnh sửa/hủy sự kiện và quản lý người tham gia/check-in; các trạng thái và quy tắc trong F04–F06.
- **Assumed:** Tên, tuổi, năm học, vai trò cụ thể trong CLB, công cụ đang dùng, thiết bị, áp lực công việc, hành vi workaround và những tình huống minh họa.
- **Inferred:** Nhóm trường của Create Event, cách trình bày dashboard, thiết kế bước xác nhận, hiển thị QR Scanner và phản hồi lỗi được suy ra từ nghiệp vụ và nhu cầu giả định.
- **Observed / Reported:** Chưa có dữ liệu quan sát hoặc lời thuật lại từ thành viên ban tổ chức thực tế.

## Open questions

- Ban tổ chức hiện dùng những công cụ nào để công bố sự kiện và quản lý đăng ký? Bước nào mất thời gian nhất?
- Người tạo sự kiện có đồng thời là người chỉnh sửa và check-in không, hay cần phân quyền nhiều thành viên?
- Thành viên thường quản lý sự kiện trên laptop, smartphone hay cả hai? Thiết bị nào được dùng khi check-in?
- Những trường thông tin nào thường bị thiếu hoặc sai khi đăng sự kiện?
- Ban tổ chức phân biệt và sử dụng các chỉ số `Registered`, `Waitlisted`, `Planning to Attend` trong quyết định vận hành như thế nào?
- Khi có chỗ trống, ban tổ chức muốn phân bổ waitlist theo quy tắc nào? Thời hạn phản hồi offer bao lâu là phù hợp?
- Khi đổi giờ, địa điểm hoặc hủy sự kiện, ban tổ chức thường thông báo cho ai và kiểm tra việc tiếp nhận thông tin bằng cách nào?
- Mỗi đợt check-in có bao nhiêu người và thường xảy ra lỗi gì khi đối chiếu vé?
- Nếu không có kết nối mạng ở cổng, quy trình xử lý an toàn của ban tổ chức là gì?
- Sau sự kiện, số liệu nào thực sự hữu ích để đánh giá chất lượng tổ chức?

## Potential UI Decisions to Test

| Nhu cầu của người dùng | Giả thuyết thiết kế UI | Cách kiểm chứng |
| :-- | :-- | :-- |
| **Công bố sự kiện đầy đủ và đúng chính sách** | Create Event chia thành các nhóm thông tin dễ hiểu, làm rõ `Audience`, `Eligibility`, `Registration Required`, `Walk-in Allowed`, `Information Only`, capacity và waitlist; có validation và `Review Event`. | Giao nhiệm vụ tạo workshop từ thông tin có sẵn, bao gồm một vài dữ liệu không hợp lệ. Quan sát người dùng nhập đúng chính sách, phát hiện trường lỗi và hiểu điều gì sẽ được công bố. |
| **Lưu nội dung chưa hoàn thiện** | `Save Draft` tách biệt rõ khỏi `Publish`, phản hồi trạng thái nháp sau khi lưu. | Yêu cầu tạo sự kiện khi còn thiếu ảnh hoặc thời gian. Kiểm tra người dùng có biết lưu nháp và hiểu rằng sự kiện chưa hiển thị cho Student hay không. |
| **Theo dõi đúng trạng thái người tham gia** | Dashboard/Event Management hiển thị `Registered`, `Waitlisted`, `Planning to Attend`, `Checked-in` bằng nhãn và giải thích rõ ràng. | Cho người dùng đọc số liệu của một sự kiện; yêu cầu xác định số đăng ký, số đang chờ, số dự định đến và số thực tế đã check-in. Ghi nhận nhầm lẫn. |
| **Chỉnh sửa sự kiện mà không gây hiểu nhầm** | Trước khi lưu thay đổi quan trọng, có bước review và xác nhận; sau khi lưu, phản hồi rõ việc cập nhật thành công hay thất bại. | Yêu cầu đổi giờ hoặc địa điểm của sự kiện đã có người đăng ký. Quan sát người dùng có nhận biết thay đổi ảnh hưởng đến ai và hiểu kết quả xử lý không. |
| **Tránh hủy sự kiện ngoài ý muốn** | `Cancel Event` dùng confirmation dialog mô tả hậu quả, khác biệt rõ với `Edit` hoặc `Back`. | Yêu cầu người dùng bắt đầu hủy rồi đổi ý. Quan sát họ có thể giữ nguyên sự kiện mà không thực hiện nhầm thao tác phá hủy hay không. |
| **Check-in nhanh nhưng chính xác** | QR Scanner phản hồi rõ ràng theo ba trạng thái `Valid`, `Duplicate`, `Invalid`; không cộng thêm check-in khi vé đã quét hoặc không hợp lệ. | Mô phỏng ba mã QR trên cùng sự kiện. Đo thời gian xác định kết quả và số lần người dùng xử lý sai hoặc hiểu nhầm trạng thái. |
| **Ứng phó khi kết nối thất bại** | Khi không xác minh được vé, hiển thị lỗi dễ hiểu và tùy chọn `Thử lại`; không tạo phản hồi check-in thành công giả. | Giả lập mất mạng khi quét QR; hỏi người dùng vé đã được ghi nhận chưa và họ sẽ làm gì tiếp theo. |
| **Biết số người đến thực tế** | `Checked-in` được trình bày tách biệt với `Registered` và `Planning to Attend`, có thể đối chiếu trên Event Management. | Sau một chuỗi check-in giả lập, yêu cầu xác định số người thực tế đã đến và giải thích vì sao khác số đăng ký. |

---

# Persona 3 - Sinh viên bận rộn

## Tên giả định & Archetype

**Trần Gia Huy — Sinh viên có lịch học dày và ít thời gian rảnh.**

- 22 tuổi, sinh viên đại học năm 3.
- Có lịch học, bài tập, deadline và các hoạt động cá nhân chiếm phần lớn thời gian trong tuần.
- Vẫn muốn tham gia hoạt động trong trường nhưng chỉ khi sự kiện thực tế phù hợp với khoảng thời gian còn trống.
- Có xu hướng ưu tiên tốc độ tìm kiếm, khả năng lưu lại và nhắc đúng lúc hơn việc dành nhiều thời gian lướt khám phá.

## Ưu tiên & lý do

- **Secondary.**
- **Lí do:** Persona này không đại diện trực tiếp nhất cho bài toán khám phá sự kiện của Camply như Primary Persona, nhưng bổ sung một nhu cầu quan trọng: giúp sinh viên có ít thời gian nhanh chóng xác định sự kiện nào thực tế phù hợp với lịch cá nhân, lưu lại sự kiện chưa thể quyết định ngay và tránh bỏ lỡ do quên.

## Usage context

- **Thời điểm:** Giữa các tiết học, ngay sau khi biết lịch rảnh, buổi tối sau khi hoàn thành việc học hoặc khi cần lên kế hoạch cho vài ngày tới.
- **Thiết bị:** Smartphone, màn hình dọc; thường muốn hoàn thành thao tác nhanh thay vì dành nhiều thời gian duyệt nội dung.
- **Môi trường:** Lớp học lúc nghỉ, thư viện, khu tự học, xe buýt hoặc khi đang di chuyển; có thể bị gián đoạn bởi lịch học, tin nhắn hoặc công việc khác.
- **Sự chú ý:** Khá thấp khi chỉ tranh thủ kiểm tra sự kiện; một phiên sử dụng khoảng 1–3 phút là giả định cần xác minh.
- **Bối cảnh quyết định:** “Mình rảnh lúc nào?” thường quan trọng trước câu hỏi “Sự kiện nào thú vị nhất?”.

## Goals

1. Nhanh chóng tìm được những sự kiện phù hợp với khoảng thời gian mình có thể tham gia.

2. Nhìn thấy ngày, giờ và thời lượng sự kiện đủ sớm để loại bỏ những sự kiện bị trùng lịch mà không cần đọc toàn bộ nội dung.

3. Lưu lại những sự kiện quan tâm khi chưa thể quyết định ngay để không phải tìm lại từ đầu.

4. Biết những sự kiện đã lưu hoặc đã đăng ký sắp diễn ra để chủ động sắp xếp thời gian.

5. Nhận nhắc nhở đủ sớm để không quên một sự kiện đã quan tâm hoặc đã đăng ký.

6. Tra lại nhanh lịch, địa điểm và trạng thái đăng ký trước khi tham gia.

## Job to Be Done

Khi có một khoảng thời gian rảnh giữa lịch học và các công việc khác, tôi muốn nhanh chóng biết sự kiện nào phù hợp với thời gian đó, lưu những sự kiện chưa thể quyết định và được nhắc trước khi chúng diễn ra, để có thể tham gia hoạt động trong trường mà không làm ảnh hưởng đến lịch cá nhân hoặc bỏ lỡ vì quên.

## Current behaviors & workaround

- Kiểm tra lịch học hoặc deadline trước khi quyết định có tham gia một sự kiện hay không.
- Khi thấy một sự kiện thú vị trên fanpage hoặc group, thường tìm ngày giờ trước khi đọc phần mô tả chi tiết.
- Có thể bỏ qua ngay một sự kiện nếu thời gian diễn ra không phù hợp, kể cả khi nội dung hấp dẫn.
- Chụp màn hình, lưu bài đăng, bookmark hoặc gửi đường dẫn vào tin nhắn để giữ lại những sự kiện chưa thể quyết định ngay.
- Có thể tạo reminder cá nhân, ghi chú hoặc tự nhớ lịch nếu sự kiện quan trọng.
- Khi quên thời gian, phải quay lại bài đăng, email, tin nhắn hoặc form đăng ký để kiểm tra.
- Giả định sử dụng smartphone trong các phiên ngắn và ưu tiên thao tác nhanh. Tần suất sử dụng lịch, reminder và cách sinh viên hiện lưu sự kiện chưa được xác minh.

## Pain points

1. **Khó biết sự kiện nào thực sự phù hợp lịch:** Ngày giờ đôi khi không đủ nổi bật → phải mở từng sự kiện để kiểm tra rồi mới biết có tham gia được hay không.

2. **Mất thời gian khi phải duyệt nhiều sự kiện không phù hợp:** Danh sách có thể chứa nhiều hoạt động hay nhưng trùng giờ học → phải tự loại bỏ từng sự kiện.

3. **Khó quay lại sự kiện đang cân nhắc:** Chưa muốn đăng ký ngay nhưng nếu chỉ lưu bài hoặc chụp màn hình thì sau đó khó nhớ đã lưu ở đâu.

4. **Dễ quên sự kiện đã quan tâm:** Có thể thấy sự kiện từ nhiều ngày trước nhưng quên đăng ký hoặc quên ngày diễn ra.

5. **Thông tin quan trọng bị lẫn với nội dung mô tả:** Phải đọc hoặc cuộn để biết thời gian, thời lượng, địa điểm và trạng thái đăng ký.

6. **Bị gián đoạn giữa chừng:** Có thể đang xem sự kiện nhưng phải quay lại lớp hoặc chuyển sang việc khác → lần sau phải tìm lại từ đầu.

## Motivations

- **Quản lý thời gian:** Muốn tham gia hoạt động nhưng không ảnh hưởng đến lịch học và deadline.
  - **UX implication:** Ngày, giờ và thời lượng sự kiện cần có visual hierarchy cao và xuất hiện sớm.

- **Tận dụng thời gian rảnh:** Muốn nhanh chóng tìm được hoạt động phù hợp với những khoảng trống trong lịch.
  - **UX implication:** Filter theo ngày/thời gian cần dễ truy cập và không yêu cầu nhiều bước.

- **Giảm gánh nặng ghi nhớ:** Không muốn phải tự nhớ hoặc tự tạo nhiều reminder bên ngoài.
  - **UX implication:** Saved Events, My Events và reminder cần có trạng thái rõ ràng.

- **Quyết định sau:** Không phải sự kiện nào quan tâm cũng có thể đăng ký ngay.
  - **UX implication:** Cần phân biệt rõ hành động `Lưu` với `Đăng ký`.

## Constraints

- **Thời gian:** Khoảng rảnh ngắn và dễ bị gián đoạn; flow dài hoặc nhiều màn hình làm tăng khả năng bỏ dở.
- **Sự chú ý:** Người dùng thường chỉ muốn xác định nhanh “có phù hợp lịch không?” trước khi đọc sâu hơn.
- **Thiết bị:** Smartphone có màn hình nhỏ; thông tin lịch không được trình bày quá dày hoặc yêu cầu so sánh nhiều cột.
- **Kỹ năng:** Mức độ quen với filter nâng cao hoặc các gesture ẩn chưa được xác minh; cần sử dụng pattern quen thuộc và label rõ.
- **Kết nối:** Có thể sử dụng trong lúc di chuyển; loading và error state phải giúp người dùng biết dữ liệu thời gian/sự kiện đã tải thành công hay chưa.
- **Accessibility:** Nhu cầu cá nhân chưa được khảo sát. Theo tình huống, giao diện cần dễ scan nhanh, vùng chạm đủ lớn và không dùng màu là dấu hiệu duy nhất của trạng thái.
- **Quyền hạn:** Là người tham gia; chỉ quản lý các sự kiện mình quan tâm hoặc đã đăng ký, không chỉnh sửa thông tin sự kiện.

## Critical scenarios

1. **Tìm sự kiện phù hợp với thời gian rảnh:** Gia Huy biết chiều thứ Sáu mình rảnh và muốn tìm một hoạt động để tham gia. Mở Camply, giới hạn danh sách theo thời gian phù hợp, xem nhanh các lựa chọn rồi mở chi tiết một sự kiện. Kết quả mong muốn là loại bỏ được sự kiện trùng lịch mà không cần mở từng sự kiện.

2. **Lưu để quyết định sau:** Gia Huy thấy một workshop thú vị nhưng chưa chắc có thể tham gia. Muốn lưu sự kiện rồi tiếp tục công việc hiện tại. Sau đó quay lại Camply và tìm được đúng sự kiện đã lưu mà không phải search lại.

3. **Nhận nhắc và tra lại:** Gia Huy đã đăng ký một sự kiện vài ngày trước nhưng đang bận học. Trước khi sự kiện diễn ra, nhận reminder, mở ứng dụng và kiểm tra nhanh thời gian, địa điểm và trạng thái đăng ký.

## Success criteria

Các mục tiêu dưới đây dùng cho prototype có dữ liệu sự kiện phù hợp; chưa có kết quả usability test thực tế.

- **Tìm theo thời gian:** Trong ≤20 giây từ Home, tìm và mở chi tiết một sự kiện phù hợp với khoảng thời gian được giao.
- **Nhận biết lịch:** Sau khi xem Event Card hoặc Event Detail, xác định đúng ngày, giờ và liệu sự kiện có phù hợp với khoảng thời gian yêu cầu mà không cần trợ giúp.
- **Lưu sự kiện:** Lưu một sự kiện đang cân nhắc và tìm lại đúng sự kiện đó trong ≤15 giây từ Home.
- **Tra lại sự kiện:** Trong ≤20 giây từ Home, tìm được một sự kiện đã đăng ký và đọc đúng thời gian, địa điểm và trạng thái.
- **Nhận biết reminder:** Khi nhận reminder giả lập, hiểu đúng sự kiện nào sắp diễn ra và biết hành động tiếp theo mà không cần giải thích.

Ghi thời gian, số bước, lỗi thao tác và mức trợ giúp. Tác vụ thành công khi người dùng hoàn tất và hiểu đúng trạng thái mà không cần gợi ý.

## Research evidence

Thông tin trong persona được xây dựng từ quá trình **research hiện trạng chung về cách sinh viên tìm kiếm, tiếp cận, đăng ký và theo dõi các sự kiện trong môi trường đại học**.

Các nội dung như hành vi hiện tại, pain points, motivations, constraints và nhu cầu được tổng hợp từ những patterns phổ biến được giả định trong bối cảnh sử dụng các kênh như fanpage trường, fanpage câu lạc bộ, nhóm sinh viên, bài chia sẻ trên mạng xã hội và các form đăng ký sự kiện.

Hiện chưa thực hiện phỏng vấn hoặc quan sát trực tiếp một nhóm người dùng cụ thể, vì vậy persona này vẫn được xem là **research-based proto-persona**. Các giả định về tần suất sử dụng, thời lượng phiên, mức độ thành thạo, hành vi cụ thể và nhu cầu accessibility vẫn cần được kiểm chứng thêm bằng usability test hoặc nghiên cứu người dùng thực tế.

## Evidence status

**Proto-Persona — chưa xác thực.**

- **Provided:** Sinh viên 18–24 tuổi, lịch học dày; muốn tìm nhanh sự kiện phù hợp lịch cá nhân, lưu sự kiện quan tâm và nhận nhắc nhở.
- **Assumed:** Tuổi cụ thể, năm học, thời lượng phiên, cách kiểm tra lịch, cách lưu sự kiện hiện tại, hành vi reminder và các critical scenarios.
- **Inferred:** Việc ưu tiên thời gian trên Event Card, filter theo thời gian, Saved Events và cách trình bày reminder được suy ra từ nhu cầu đã mô tả.
- **Observed / Reported:** Chưa có dữ liệu từ người tham gia nghiên cứu thực tế.

## Open questions

- Khi cân nhắc tham gia sự kiện, sinh viên kiểm tra lịch học trước hay xem nội dung sự kiện trước?
- Khoảng thời gian nào cần filter: ngày, buổi sáng/chiều/tối hay giờ cụ thể?
- Sinh viên hiện lưu sự kiện quan tâm bằng cách nào?
- Có phân biệt rõ trong suy nghĩ giữa “lưu để xem sau” và “đã đăng ký” hay không?
- Reminder nên xuất hiện trước sự kiện bao lâu để thực sự hữu ích?
- Người dùng muốn được nhắc cho sự kiện đã lưu, chỉ sự kiện đã đăng ký hay cả hai?
- Việc tích hợp lịch cá nhân có thực sự cần thiết hay chỉ cần hiển thị rõ ngày giờ trong Camply?
- Người dùng có thường tham gia các sự kiện kéo dài nhiều giờ hoặc trùng một phần lịch học không?

## Potential UI Decisions to Test

| Nhu cầu của người dùng | Giả thuyết thiết kế UI | Cách kiểm chứng |
| :-- | :-- | :-- |
| **Tìm sự kiện phù hợp với thời gian rảnh** | Home/Search cần có bộ lọc thời gian dễ truy cập như `Hôm nay`, `Ngày mai`, `Tuần này` hoặc ngày cụ thể. Event Card cần hiển thị ngày và giờ đủ nổi bật để người dùng loại nhanh các sự kiện không phù hợp. | Giao nhiệm vụ: **“Bạn rảnh chiều thứ Sáu. Hãy tìm một sự kiện mà bạn có thể tham gia.”** Quan sát người dùng có tìm thấy filter thời gian không, có phải mở nhiều Event Detail để kiểm tra giờ không và mất bao lâu để chọn được một sự kiện phù hợp. |
| **Đánh giá lịch mà không cần đọc nhiều** | Date, Time và Duration cần có visual hierarchy cao hơn các metadata phụ trên Event Card và Event Detail. | Cho người dùng xem một nhóm Event Card rồi hỏi sự kiện nào phù hợp với một khoảng thời gian cụ thể. Quan sát họ có đọc đúng lịch ngay trên card hay phải mở từng sự kiện hoặc đọc mô tả dài. |
| **Lưu sự kiện để quyết định sau** | Mỗi sự kiện cần có hành động `Lưu` dễ nhận biết nhưng không cạnh tranh với CTA `Đăng ký`. Các sự kiện đã lưu phải có một nơi tập trung để tìm lại. | Yêu cầu: **“Bạn thấy sự kiện này thú vị nhưng chưa muốn đăng ký. Hãy lưu lại để xem sau.”** Sau đó chuyển sang màn hình khác và yêu cầu tìm lại sự kiện. Quan sát người dùng có phân biệt `Lưu` và `Đăng ký`, có biết tìm Saved Events ở đâu và mất bao lâu để tra lại. |
| **Không quên sự kiện sắp diễn ra** | Reminder cần nói rõ tên sự kiện, thời gian bắt đầu và thông tin đủ để người dùng nhận biết ngay sự kiện nào đang được nhắc. | Hiển thị notification/reminder giả lập rồi hỏi: **“Thông báo này đang nhắc bạn về việc gì và bạn sẽ làm gì tiếp theo?”** Quan sát người dùng có hiểu đúng sự kiện, thời gian và có biết cách mở chi tiết hay không. |
| **Tiếp tục sau khi bị gián đoạn** | Các trạng thái `Saved` và `Registered` phải tồn tại rõ ràng để khi quay lại ứng dụng, người dùng không cần nhớ mình đã làm gì trước đó. | Cho người dùng lưu hoặc đăng ký một sự kiện, chuyển sang một tác vụ khác rồi quay lại Camply. Yêu cầu xác định sự kiện đang ở trạng thái nào và tiếp tục từ đó. Quan sát xem trạng thái có đủ rõ để người dùng không lặp lại thao tác. |
| **Tra lại nhanh sự kiện đã đăng ký** | `My Events` cần dễ truy cập và ưu tiên `Upcoming` để người dùng bận rộn thấy ngay sự kiện gần nhất. | Yêu cầu người dùng từ Home tìm sự kiện đã đăng ký sắp diễn ra gần nhất. Đo số thao tác, thời gian và việc họ có đọc đúng ngày giờ, địa điểm hay không. |

---

# Persona 4 — Sinh viên năm nhất

## Tên giả định & Archetype

**Lê Thảo Vy — Sinh viên năm nhất đang làm quen với môi trường đại học.**

- 18 tuổi, sinh viên đại học năm nhất.
- Mới bắt đầu làm quen với môi trường, câu lạc bộ, địa điểm và cách trường truyền thông về các hoạt động.
- Muốn tham gia hoạt động để kết bạn, trải nghiệm đời sống sinh viên và cảm thấy mình thuộc về cộng đồng.
- Chưa biết nên theo dõi fanpage nào, câu lạc bộ nào hoặc bắt đầu tìm sự kiện từ đâu.

## Ưu tiên & lý do

- **Secondary.**
- **Lí do:** Persona này vẫn có nhu cầu khám phá sự kiện giống Primary Persona nhưng rào cản chính khác nhau. Thảo Vy không chỉ thiếu một nơi tổng hợp sự kiện mà còn **thiếu kiến thức về hệ sinh thái trong trường**: chưa biết câu lạc bộ, đơn vị tổ chức, địa điểm hoặc hoạt động nào phù hợp với sinh viên mới.

Persona này giúp kiểm tra liệu Camply có thể hỗ trợ người dùng mới khám phá mà không yêu cầu họ phải hiểu trước cấu trúc của trường.

## Usage context

- **Thời điểm:** Những tuần đầu học kỳ, thời gian orientation, giữa các tiết học hoặc khi muốn tìm hoạt động ngoài giờ.
- **Thiết bị:** Smartphone, màn hình dọc; có thể sử dụng ngay khi đang ở trong khuôn viên trường.
- **Môi trường:** Khuôn viên chưa quen thuộc, lớp học, ký túc xá, căn tin, thư viện hoặc khi đi cùng bạn mới.
- **Sự chú ý:** Có thể dành nhiều thời gian khám phá hơn Persona 3 nhưng vẫn cần thông tin đơn giản, dễ hiểu vì nhiều tên CLB, địa điểm và thuật ngữ còn mới.
- **Bối cảnh kiến thức:** Chưa chắc biết tên đơn vị tổ chức hoặc tên sự kiện để search trực tiếp.

## Goals

1. Khám phá những hoạt động phù hợp với sinh viên mới ngay cả khi chưa biết tên câu lạc bộ hoặc đơn vị tổ chức.

2. Tìm những hoạt động có cơ hội gặp gỡ, giao lưu hoặc làm quen với sinh viên khác.

3. Hiểu sự kiện dành cho ai, cần chuẩn bị gì và có phù hợp với sinh viên năm nhất hay không.

4. Biết rõ địa điểm tổ chức để tự tin đến tham gia trong một khuôn viên còn chưa quen.

5. Hiểu câu lạc bộ hoặc đơn vị nào đang tổ chức sự kiện mà không cần biết trước về họ.

6. Đăng ký và lưu lại những hoạt động quan tâm để dần xây dựng kế hoạch tham gia đời sống sinh viên.

## Job to Be Done

Khi mới vào đại học và chưa biết có những câu lạc bộ hoặc hoạt động nào, tôi muốn dễ dàng khám phá những sự kiện phù hợp với sinh viên mới, hiểu chúng dành cho ai và diễn ra ở đâu, để có thể tham gia, kết bạn và hòa nhập với môi trường đại học mà không cần biết trước các kênh thông tin của trường.

## Current behaviors & workaround

- Hỏi bạn cùng lớp, sinh viên khóa trên hoặc người quen xem trường có hoạt động nào đáng tham gia.
- Biết đến sự kiện thông qua orientation, group lớp, group tân sinh viên hoặc bài được người khác chia sẻ.
- Có thể theo dõi một số fanpage được giới thiệu nhưng chưa biết còn những CLB hoặc đơn vị nào khác.
- Khi thấy tên một CLB chưa quen, có thể phải mở fanpage hoặc tìm kiếm thêm để hiểu CLB đó làm gì.
- Khi địa điểm dùng tên tòa nhà/phòng chưa quen, có thể hỏi bạn bè, tra bản đồ hoặc tìm biển chỉ dẫn.
- Có thể ưu tiên sự kiện được mô tả là dành cho sinh viên mới, giao lưu, workshop nhập môn hoặc hoạt động có tính cộng đồng.
- Giả định smartphone là thiết bị chính. Mức độ chủ động tham gia hoạt động, mức độ lo lắng khi tham gia một mình và kênh thông tin thực tế chưa được xác minh.

## Pain points

1. **Không biết bắt đầu tìm ở đâu:** Chưa biết fanpage, CLB hoặc group nào cần theo dõi → phụ thuộc vào bạn bè hoặc tình cờ thấy bài đăng.

2. **Không biết tên để tìm kiếm:** Search theo tên CLB hoặc tên event ít hữu ích nếu người dùng chưa biết các tên đó tồn tại.

3. **Khó hiểu một sự kiện có phù hợp hay không:** Nội dung có thể giả định người đọc đã biết CLB, thuật ngữ hoặc nhóm đối tượng → sinh viên mới không chắc mình có thể tham gia.

4. **Thiếu cảm giác tự tin khi tham gia một mình:** Không biết hoạt động có phù hợp để gặp người mới hoặc có thân thiện với người chưa quen ai hay không.

5. **Địa điểm chưa quen:** Tên tòa nhà hoặc phòng học không đủ để người mới hình dung vị trí.

6. **Quá nhiều thông tin mới:** Nhiều CLB, hoạt động và tên đơn vị xuất hiện cùng lúc → khó biết cái nào đáng quan tâm trước.

## Motivations

- **Kết bạn:** Muốn gặp những sinh viên có cùng sở thích và xây dựng mối quan hệ mới.
  - **UX implication:** Category hoặc nội dung cần giúp nhận biết các sự kiện có tính giao lưu, cộng đồng hoặc phù hợp cho người mới.

- **Hòa nhập:** Muốn hiểu thêm về đời sống đại học ngoài giờ học.
  - **UX implication:** Home cần cho phép khám phá theo nhu cầu/chủ đề thay vì yêu cầu biết tên CLB.

- **Khám phá bản thân:** Muốn thử nhiều loại hoạt động để biết mình phù hợp với cộng đồng hoặc sở thích nào.
  - **UX implication:** Giao diện nên khuyến khích browse nhiều category khác nhau và không tạo cảm giác chỉ dành cho người đã biết mình muốn gì.

- **Tự tin tham gia:** Muốn biết rõ ai tổ chức, sự kiện dành cho ai, cần làm gì và đi đâu.
  - **UX implication:** Event Detail phải giảm sự mơ hồ bằng thông tin rõ ràng, không giả định kiến thức trước.

## Constraints

- **Kiến thức về trường:** Chưa biết nhiều tên CLB, khoa, tòa nhà hoặc kênh truyền thông → giao diện không được phụ thuộc vào kiến thức nội bộ.
- **Từ vựng:** Tên viết tắt hoặc thuật ngữ riêng của trường có thể khó hiểu; cần label và mô tả rõ.
- **Kinh nghiệm:** Chưa biết quy trình đăng ký sự kiện thường diễn ra như thế nào hoặc sau đăng ký cần làm gì.
- **Thiết bị:** Chủ yếu dùng smartphone; khi đang trong khuôn viên trường có thể vừa đi vừa kiểm tra địa điểm.
- **Sự tự tin:** Có thể do dự khi sự kiện không nói rõ đối tượng hoặc không biết có thể tham gia một mình hay không. Đây là giả định cần nghiên cứu thêm, không phải đặc điểm đã xác minh.
- **Accessibility:** Nhu cầu cá nhân chưa được khảo sát. Nội dung cần chữ dễ đọc, label rõ, vùng chạm đủ lớn và không dùng màu làm dấu hiệu duy nhất.
- **Quyền hạn:** Là người tham gia; không quản trị CLB hoặc chỉnh sửa nội dung sự kiện.

## Critical scenarios

1. **Tìm hoạt động để kết bạn:** Trong những tuần đầu đại học, Thảo Vy muốn tham gia một hoạt động có thể gặp gỡ người mới nhưng không biết tên câu lạc bộ nào. Mở Camply, duyệt theo chủ đề hoặc loại hoạt động, xem một số sự kiện rồi chọn một hoạt động phù hợp.

2. **Đánh giá sự kiện chưa từng biết:** Thảo Vy thấy một sự kiện do một CLB chưa từng nghe tên tổ chức. Mở Event Detail để hiểu nội dung, đối tượng, đơn vị tổ chức, yêu cầu tham gia, ngày giờ và địa điểm trước khi quyết định.

3. **Tìm đường đến sự kiện:** Trước giờ bắt đầu, Thảo Vy mở lại sự kiện đã đăng ký để kiểm tra địa điểm. Kết quả mong muốn là hiểu đủ thông tin để biết mình cần đến đâu mà không phải quay lại bài đăng bên ngoài.

## Success criteria

Các mục tiêu dưới đây dùng cho prototype; chưa có dữ liệu usability test thực tế.

- **Khám phá:** Trong ≤30 giây từ Home, tìm và mở một sự kiện có mục đích giao lưu/kết nối mà không cần biết trước tên sự kiện hoặc CLB.
- **Hiểu sự kiện:** Sau khi xem Event Detail, nêu đúng sự kiện nói về điều gì, dành cho ai, khi nào và ở đâu mà không cần mở nguồn bên ngoài.
- **Nhận biết organizer:** Xác định được đơn vị tổ chức và hiểu cơ bản đơn vị đó là ai từ thông tin trong Camply.
- **Đăng ký:** Hoàn thành đăng ký một sự kiện phù hợp và hiểu đúng trạng thái đăng ký mà không cần trợ giúp.
- **Tra địa điểm:** Trong ≤20 giây từ My Events, tìm lại sự kiện được yêu cầu và đọc đúng địa điểm tổ chức.

Ghi thời gian, lỗi thao tác, câu hỏi người dùng đặt ra và mức trợ giúp. Tác vụ thành công khi người dùng hoàn tất và hiểu đúng nội dung mà không cần giải thích từ người test.

## Research evidence

Thông tin trong persona được xây dựng từ quá trình **research hiện trạng chung về cách sinh viên tìm kiếm, tiếp cận, đăng ký và theo dõi các sự kiện trong môi trường đại học**.

Các nội dung như hành vi hiện tại, pain points, motivations, constraints và nhu cầu được tổng hợp từ những patterns phổ biến được giả định trong bối cảnh sử dụng các kênh như fanpage trường, fanpage câu lạc bộ, nhóm sinh viên, bài chia sẻ trên mạng xã hội và các form đăng ký sự kiện.

Hiện chưa thực hiện phỏng vấn hoặc quan sát trực tiếp một nhóm người dùng cụ thể, vì vậy persona này vẫn được xem là **research-based proto-persona**. Các giả định về tần suất sử dụng, thời lượng phiên, mức độ thành thạo, hành vi cụ thể và nhu cầu accessibility vẫn cần được kiểm chứng thêm bằng usability test hoặc nghiên cứu người dùng thực tế.

## Evidence status

**Proto-Persona — chưa xác thực.**

- **Provided:** Sinh viên 18–20 tuổi, mới làm quen với môi trường đại học; muốn tìm hoạt động để kết bạn và hòa nhập; chưa biết CLB hoặc các kênh sự kiện của trường.
- **Assumed:** Tên, tuổi cụ thể, hành vi hỏi bạn bè, mức độ quen địa điểm, lo lắng khi tham gia một mình và các workaround.
- **Inferred:** Việc ưu tiên discovery theo category, giới thiệu organizer, giải thích đối tượng tham gia và làm rõ location được suy ra từ nhu cầu đã mô tả.
- **Observed / Reported:** Chưa có dữ liệu từ người tham gia nghiên cứu thực tế.

## Open questions

- Sinh viên năm nhất hiện biết đến sự kiện đầu tiên của trường bằng cách nào?
- Họ thường hỏi ai khi không biết trường có hoạt động gì?
- “Muốn kết bạn” ảnh hưởng đến việc chọn sự kiện như thế nào?
- Thông tin nào khiến một sinh viên mới cảm thấy một sự kiện phù hợp với mình?
- Có cần label như `Phù hợp cho sinh viên năm nhất` hay người dùng thích category theo chủ đề hơn?
- Người dùng có cần biết thông tin chi tiết về CLB trước khi quyết định tham gia event không?
- Địa điểm trong trường khó hiểu ở mức nào? Tên tòa nhà có đủ hay cần thêm mô tả/bản đồ?
- Sinh viên mới có thường đi sự kiện một mình không, và điều gì khiến họ cảm thấy yên tâm hơn?
- Những thuật ngữ hoặc viết tắt nào của trường thường gây khó hiểu?

## Potential UI Decisions to Test

| Nhu cầu của người dùng | Giả thuyết thiết kế UI | Cách kiểm chứng |
| :-- | :-- | :-- |
| **Khám phá khi chưa biết tên CLB hoặc sự kiện** | Home cần hỗ trợ duyệt theo nhu cầu/chủ đề như `Giao lưu`, `Workshop`, `Âm nhạc`, `Thể thao`, thay vì yêu cầu người dùng search bằng tên cụ thể. | Giao nhiệm vụ: **“Bạn là sinh viên mới và muốn tìm một hoạt động để gặp gỡ người khác. Hãy tìm một sự kiện phù hợp.”** Không cung cấp tên event hoặc CLB. Quan sát người dùng bắt đầu ở đâu, category nào họ chọn, có cần Search hay không và mất bao lâu để tìm được sự kiện. |
| **Biết sự kiện có phù hợp với mình hay không** | Event Detail cần nói rõ nội dung, đối tượng tham gia, yêu cầu đăng ký và các điều kiện quan trọng bằng ngôn ngữ dễ hiểu. | Cho người dùng xem Event Detail của một sự kiện chưa biết trước rồi hỏi: **“Bạn có nghĩ mình có thể tham gia sự kiện này không? Vì sao?”** Quan sát thông tin nào họ dùng để quyết định và phần nào còn gây mơ hồ. |
| **Hiểu đơn vị tổ chức khi chưa biết CLB** | Tên organizer cần có mô tả ngắn hoặc đường dẫn đến thông tin cơ bản về đơn vị, thay vì chỉ hiển thị tên/viết tắt. | Hiển thị sự kiện từ một CLB giả định mà người dùng chưa biết. Hỏi: **“Ai đang tổ chức sự kiện này và bạn hiểu gì về họ?”** Quan sát người dùng có đủ thông tin từ UI hay phải tìm bên ngoài. |
| **Tìm hoạt động giúp giao lưu** | Các event có tính kết nối xã hội cần được nhận biết qua category hoặc mô tả, không chỉ dựa vào hình ảnh quảng bá. | Yêu cầu người dùng chọn giữa nhiều event để tìm hoạt động phù hợp với mục tiêu kết bạn. Hỏi lý do lựa chọn và quan sát tín hiệu UI nào đã giúp họ nhận biết. |
| **Hiểu địa điểm trong môi trường chưa quen** | Event Detail cần làm location nổi bật; nếu scope cho phép, có thể bổ sung mô tả tòa nhà hoặc hành động mở vị trí thay vì chỉ ghi tên phòng. | Giao nhiệm vụ: **“Bạn đã đăng ký sự kiện này và giờ cần biết mình phải đến đâu.”** Quan sát người dùng có tìm thấy location ngay không và liệu thông tin hiển thị có đủ để họ hiểu vị trí hay vẫn cần hỏi người khác. |
| **Không bị choáng bởi quá nhiều lựa chọn** | Home cần có nhóm/category rõ ràng và số lượng nội dung ưu tiên vừa phải thay vì hiển thị một danh sách dài không cấu trúc. | Cho người dùng mở Home lần đầu và yêu cầu nói họ sẽ bắt đầu từ đâu. Quan sát họ có hiểu các nhóm nội dung, có bị phân vân giữa quá nhiều lựa chọn hoặc bỏ qua section quan trọng hay không. |
| **Biết đã đăng ký thành công dù chưa quen quy trình** | Sau khi đăng ký cần có confirmation rõ và trạng thái `Đã đăng ký`; My Events phải là nơi có thể tìm lại sự kiện. | Yêu cầu người dùng đăng ký một event rồi hỏi: **“Bạn đã đăng ký thành công chưa? Nếu ngày mai muốn xem lại sự kiện này, bạn sẽ vào đâu?”** Quan sát họ có hiểu feedback và tìm đúng My Events hay không. |
