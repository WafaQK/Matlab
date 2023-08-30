%%Identifying trees using color display values
%[A, R, bbox] = geotiffread("E:\Final thesis_code\Final Code (11-11-13)\Knox\e3510n58045_SAM.tif");
[A, R, bbox] = geotiffread("C:\Users\Wafa Khan\Pictures\Atikenvale_sample02.tif");
% Generate synthetic image with Gaussian noise

% Load a hyperspectral image (replace 'hyperspectral_image.tif' with your file path)

% Select a specific band to display (e.g., band 20)
selected_band = A(:,:,3);
bands = A(:,:,:);

% Display the band values
disp('Band values:');
disp(squeeze(bands));
% Display the selected band
imshow(selected_band, []);
title('Hyperspectral Image');
colormap jet; % Apply a colormap (optional)
colorbar; % Display a colorbar (optional)
% Load the hyperspectral image (replace 'hyperspectral_image.tif' with your file path)


% Define the desired range for band values
lower_threshold = 1;
upper_threshold = 47;
lower_threshold2 = 20;
upper_threshold2 = 26;
% Create a mask that identifies pixels within the desired range
mask = (A >= lower_threshold) & (A <= upper_threshold);
%%mask2 = (A >= lower_threshold2) & (A <= upper_threshold2);
% Apply the mask to the hyperspectral image
filtered_image = A .* uint8(mask);
%%filtered_image2 = filtered_image .* uint8(mask2);
% Display the filtered image
imshow(filtered_image);
title('Filtered Hyperspectral Image (Band values between 1 and 47)');
colormap jet;
colorbar;
%imshow(filtered_image2);
%%title('Filtered Hyperspectral Image (Band values between 1 and 26)');
%%colormap jet;
%%colorbar;
gray_image = rgb2gray(filtered_image);

% Display the grayscale image
imshow(gray_image);
title('Grayscale Image');

threshold = 22; % For example

% Convert grayscale image to binary image using thresholding
binary_image = gray_image > threshold;

% Display the binary image
imshow(binary_image);
title('Binary Image');


% Find boundaries in the binary image
boundaries = bwboundaries(binary_image);


% Display the original binary image
imshow(binary_image);
hold on;
% Plot the boundaries on top of the binary image
for k = 1:length(boundaries)
    boundary = boundaries{k};
    plot(boundary(:,2), boundary(:,1), 'r', 'LineWidth', 2);
end

title('Boundaries of Binary Image');
hold off;
